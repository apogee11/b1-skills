---
title: Collecting and Exporting Telemetry Data for Performance Analysis
source: pdf pp. 124-127, sec 9.2.10.1.2
summary: Procedure for obtaining the correlation ID and exporting the Jaeger trace, Loki logs and Prometheus metrics for an SAP Support incident, the list of items to attach, and troubleshooting.
---

# Collecting and Exporting Telemetry Data for Performance Analysis

- [Prerequisites](#prerequisites)
- [Context](#context)
- [Procedure](#procedure)
- [Information to Attach to the Support Incident](#information-to-attach-to-the-support-incident)
- [Troubleshooting](#troubleshooting)

## Prerequisites

- The SAP Business One, Web Client services have the parameter `<PERF_ANA>` set to **OTEL** or **ALL** on all services.
- The OpenTelemetry collector and Grafana environment, including Jaeger for traces and Loki for logs, are running and receiving telemetry data.
- The performance issue has been reproduced while telemetry collection was active.

## Context

When reporting a performance issue in SAP Business One, Web client, SAP Support may request telemetry data, such as distributed traces, logs, or metrics exported from Grafana.

<!-- table: t125-01 -->
This procedure explains how to collect and export the required information from your environment to the SAP Support environment for analysis.

## Procedure

1. Obtain the correlation ID. The correlation ID is the primary key for locating a trace. It is propagated through all SAP Business One, Web client microservices as the `<X-B1-CorrelationId>` HTTP header.
   - a. Open the browser developer tools by pressing `F12`.
   - b. Select the *Network* tab.
   - c. In SAP Business One, Web client, reproduce the operation that experienced the performance issue.
   - d. Select any request sent to the SAP Business One, Web client. For example, a request to `/gate/...`.
   - e. In the *Request Headers* or *Response Headers* panel, locate the `<X-B1-CorrelationId>` header.
   - f. Copy the correlation ID value. The value is typically a 32-character hexadecimal string. For example, `63173cb11fae4ac6a9ae88af016b4ca9`.
2. Export the distributed trace from Jaeger. Jaeger provides a built-in `JSON` export that can be used to share a trace.
   - a. Open *Jaeger UI*. You may use `http://<host>:16686`.
   - b. In the *Search* panel on the left, perform the following steps:
     1. Leave the *Service* field as is, or select any SAP Business One, Web client service.
     2. In the *Tags* field, paste the correlation ID using the following format: `b1.correlation_id=<correlationId>`.
     3. Set the time range to cover the period when the issue occurred.
     4. Choose *Find Traces*.
   - c. In the search results, select the matching trace to open the trace details.
   - d. Export the trace using one of the following methods:
     - Choose *Download* in the trace detailed view.
     - Access the trace directly through the Jaeger API:`http://<host>:16686/api/traces/ <correlationId>`
   - e. Save the exported `JSON` file using the following naming convention: `trace-<correlationId>- <YYYYMMDD>.json`.

   Alternatively, you can export the trace directly without opening the Jaeger UI by using the Jaeger HTTP API:

   ```bash
   curl "https://<host>:16686/api/traces/<correlationId>" -o

   trace-<correlationId>-<YYYYMMDD>.json
   ```

3. Export logs for the same time range from Loki.
   - a. In Grafana *Explore*, switch the data source to *Loki*.
   - b. Run the following logQL query: `{job=~"b1-webclient.*"} |= "<correlationId>`.

     > **Note**
     >
     > Replace `<correlationId>` with the value obtained in step 1.

   - c. Set the time range to include at least 5 minutes before and 5 minutes after the affected operation.
   - d. Choose *Run query*.
   - e. Choose *Download* above the log results and select `TXT` or `JSON` format.
   - f. Save the file using one of the following naming conventions:
     - `logs-<correlationId>-<YYYYMMDD>.txt`
     - `logs-<correlationId>-<YYYYMMDD>.json`
4. Export metrics dashboard (Optional).

   Use this procedure when the issue involves sustained high latency or resource exhaustion rather than a single slow request.

   You may use Prometheus Range Query Export method to export raw metric data as a JSON file that can be inspected offline without Grafana access.

   - a. Run the following command, adjusting the metric name, host, time range, and step:

     ```bash
     curl -G "https://<prometheus-host>:9090/api/v1/query_range" \
     --data-urlencode
     "query=http_server_request_duration_seconds_bucket{job=~\"b1-
     webclient.*\"}" \
     --data-urlencode "start=2026-07-18T13:40:00Z" \ --data-urlencode
     "end=2026-07-18T13:50:00Z" \
     --data-urlencode "step=15s" \
     -o metrics-<metric>-<YYYYMMDD>.json
     ```

   - b. Repeat for each metric of interest and attach the files to the support case.

     > **Note**
     >
     > The output is a raw Prometheus JSON response, which can be read with a script or spreadsheet tool. However, it cannot be visualized interactively in Grafana without re-importing into a Prometheus instance as it requires command-line access on the support side.
     >
     > The option to perform offline analysis of the exported file using general-purpose tools is always available.

5. Record the time range. Record the exact time range, during which the issue occurred, in UTC.

   Example:

   Start: 2026-07-18 13:45:00 UTC

   End: 2026-07-18 13:46:30 UTC

## Information to Attach to the Support Incident

<!-- table: t126-01 -->
| Item | Required |
|---|---|
| `trace-<correlationId>-<date>.json` | Yes |
| `logs-<correlationId>-<date>.txt` | Yes |
| `dashboard-<date>-<description>.json` | Optional |
| Time range (UTC) | Yes |
| SAP Business One, Web client version | Yes |

## Troubleshooting

- No trace is found for the correlation ID in Jaeger.
  - Verify that `<PERF_ANA=OTEL>` or `<PERF_ANA=ALL>` is configured on all services.
  - Ensure that all services were restarted after the configuration change.
  - Verify that the OpenTelemetry collector is configured to forward traces to the Jaeger collector endpoint.
    - Default for gRPC: `14250`
    - Default for HTTP: `14268`
  - Confirm that the selected time range includes the period when the issue occurred.
- Jaeger API export returns an empty data array.
  - The trace may have expired. Verify that the Jaeger storage retention configuration covers the date when the issue occurred.
  - Verify that the correct Jaeger host name and port are used in the API request.
- Correlation ID is not visible in browser network tab.
  - The `<X-B1-CorrelationId>` header is added by the Gate service.
  - If the header is missing, the request may not have reached the Gate service, or the Gate service may have failed to inject the `<PERF_ANA>` header.
- Loki query returns no results.
  - Run the following broader query to verify that logs are being ingested: `{job=~"b1-webclient.*"}`
  - After confirming log ingestion, refine the query by adding the correlation ID filter.
