---
title: Using OpenTelemetry to Address Performance Issues
source: pdf pp. 123-124, sec 9.2.10.1.1
summary: Prerequisites and steps for finding the trace ID in the Web client and viewing traces, metrics and logs in Grafana with Jaeger, Prometheus and Loki.
---

# Using OpenTelemetry to Address Performance Issues

## Prerequisites

Ensure the following prerequisites are met:

- OpenTelemetry must be installed and enabled. For more information, see [Monitoring Performance with OpenTelemetry](opentelemetry-setup.md#monitoring-performance-with-opentelemetry) [page 119].
- OpenTelemetry collectors and visualization tools must be installed.

## Context

> **Note**
>
> All steps explained in this topic have been performed in an environment where the OpenTelemetry Collector and visualization tools have been installed on the same server. You may install them on different servers.

You can use OpenTelemetry for tracing any performance issues you might face across services in Web client. This feature supports two output modes:

- Local log: Writes performance trace entries to local log files.
- OpenTelemetry (OTEL): Exports traces, metrics, and logs to an OTEL collector for visualization in Grafana, Jaeger, and more.

> **Note**
>
> Local logging and OpenTelemetry export can be enabled simultaneously.

## Procedure

> **Note**
>
> The following procedure includes steps to be performed in Grafana.

1. Retrieve the trace ID.
   - a. Open SAP Business One, Web client.
   - b. Open your browser’s developer tools.
   - c. Perform the action that exhibits the performance issue.
   - d. Inspect the request or response headers.
   - e. Locate the `X-B1-CorrelationId` header.
   - f. Copy the trace ID value.
2. View traces.
   - a. Open Grafana.
   - b. Select the *Explore* menu.
   - c. Select Jaeger as the data source.
   - d. Search by service name or tace ID.
   - e. Choose *Run Query*.
3. View metrics.
   - a. Open Grafana.
   - b. Select the *Explore* menu.
   - c. Select Prometheus as the data source.
   - d. Query metrics such as:
     - http_server_request_duration
     - jvm_memory_used
     - process_cpu_usage
4. View Logs.
   - a. Open Grafana.
   - b. Select the *Explore* menu.
   - c. Select Loki as the data source.
   - d. Filter logs by service name or trace ID.
   - e. Choose *Show logs* to correlate log entries with traces.
