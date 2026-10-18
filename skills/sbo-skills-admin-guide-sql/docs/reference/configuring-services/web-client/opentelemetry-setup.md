---
title: "OpenTelemetry for the Web Client: Enabling, Data Collected, Configuration"
source: pdf pp. 119-123, sec 9.2.10.1*
summary: Recommended software, the environment variables that enable OpenTelemetry in the Web client, the traces, metrics and logs collected, recommended settings, and service name abbreviations.
---

# OpenTelemetry for the Web Client: Enabling, Data Collected, Configuration

- [Monitoring Performance with OpenTelemetry](#monitoring-performance-with-opentelemetry)
- [Recommended Software](#recommended-software)
- [Enabling OpenTelemetry](#enabling-opentelemetry)
- [Telemetry Data Collected for Analysis](#telemetry-data-collected-for-analysis)
- [Recommended Configuration](#recommended-configuration)
- [Additional Information](#additional-information)

## Monitoring Performance with OpenTelemetry

To address a performance issue with any of the services in Web client, you need to collect traces, metrics, and logs. You can then use the findings to identify the source of the issue affecting the performance of the service and take appropriate action to improve it. Web client supports using OpenTelemetry (OTEL) with collector visualization tools to collect data to analyze and take action to improve the service performance.

## Recommended Software

We recommend using the following software, which are available to download:

- OpenTelemetry collectors at https://opentelemetry.io/
- OpenTelemetry visualization tools at:
  - Grafana: https://grafana.com/
  - Jaeger (distributed tracing): https://www.jaegertracing.io/
  - Prometheus (metrics collection): https://prometheus.io/
  - Loki (log aggregation): https://grafana.com/oss/loki/

## Enabling OpenTelemetry

To enable OpenTelemetry, set the following environment variables:

Required

<!-- table: t120-01 -->
- **Variable**: `<PERF_ANA>`
  - **Value**: `log` / `otel` / `all`
  - **Description**:

    Specifies the performance analysis mode.

    - `Log`: Writes performance data to local log files only.
    - `Otel`: Exports telemetry data to OpenTelemetry only.
    - `All`: Enables both local logging and OpenTelemetry export.

- **Variable**: `<PERFLOGGING_LEVEL>`
  - **Value**: `DEBUG` / `INFO`
  - **Description**:

    Controls the level of detail written to local log files when local logging is enabled.

    - `DEBUG`: Includes database calls.
    - `INFO`: Excludes database calls.

Optional (OpenTelemetry)

<!-- table: t120-02 -->
| Variable | Default | Description |
|---|---|---|
| `<OTEL_EXPORTER_ENDPOINT>` | `http://localhost:4317` (gRPC) or `http://localhost:4318` (HTTP) | The OTLP collector endpoint. |
| `<OTEL_EXPORTER_PROTOCOL>` | `grpc` | Transport protocol: `grpc` or `http/protobuf`. |
| `<OTEL_TRACES_SAMPLER>` | `always_on` | Sampling strategy: `always_on`, `always_off`, or `traceidratio`. |
| `<OTEL_TRACES_SAMPLER_ARG>` | `1.0` | Sampling ratio when sampler is `traceidratio` (range 0.0–1.0). |
| `<OTEL_METRIC_INTERVAL_SECONDS>` | `60` | How often metrics are exported (in seconds). |

> **Note**
>
> After modifying environment variables, restart all Web client services for the changes to take effect.

## Telemetry Data Collected for Analysis

When OpenTelemetry is enabled (`PERF_ANA=otel` or `all`), the following telemetry data is sent from SAP Business One, Web client to Grafana by the collectors:

### Traces

The following trace data is collected:

- HTTP server spans for incoming requests
- HTTP client spans, including:
  - Service Layer calls
  - Microsoft 365 calls
  - SAP Business One analytics powered by SAP HANA calls
  - Other external service calls
- Database spans for SQL queries (with sensitive data masked)
- Internal spans for inter-service communication
- Trace context propagation across services by using `X-B1-CorrelationId` / `X-B1-SpanId` headers

> **Note**
>
> The minimum data retention period for traces is 30 days.

### Metrics

The following metrics are collected:

- Total number of HTTP requests: `http.server.request.count`
- Total number of HTTP errors (4xx and 5xx): `http.server.error.count`
- Request duration histogram (milliseconds): `http.server.request.duration`
- Process CPU utilization: `process.cpu.usage`
- System CPU utilization: `system.cpu.usage`
- JVM heap and non-heap memory usage: `jvm.memory.used`
- Maximum JVM heap memory: `jvm.memory.max`
- Available JVM memory: `jvm.memory.free`
- Available physical memory: `system.memory.total` / `system.memory.free`

> **Note**
>
> The minimum data retention period for metrics is 90 days.

### Logs

Application logs are forwarded to the OpenTelemetry collector by using a Logback appender (OtelLogAppender). The exported log data includes:

- Log severity level
- Mapped Diagnostic Context (MDC) information, including trace ID
- Exception details

## Recommended Configuration

We recommend the following variable settings:

<!-- table: t122-01 -->
| Variable | When to Use |
|---|---|
| `<PERF_ANA=log>` and `<PERFLOGGING_LEVEL=INFO>` | Lightweight local troubleshooting without database-level details. |
| `<PERF_ANA=log>` and `<PERFLOGGING_LEVEL=DEBUG>` | Troubleshooting when database activity may be contributing to the issue. |
| `<PERF_ANA=otel>` | Distributed tracing, cross-service correlation, metrics monitoring, and visualization through Grafana and Jaeger. |
| `<PERF_ANA=all>` | Simultaneous local logging and OpenTelemetry export. |

> **Note**
>
> After modifying environment variables, restart all Web client services for the changes to take effect.

## Additional Information

The following table lists some common service name abbreviations and their descriptions:

<!-- table: t122-02 -->
| Abbreviation | Description |
|---|---|
| Page | Web browser page |
| Gate | API Gateway |
| Auth | Web Client Authentication |
| Tcli | Web Client Main Business |
| Extn | Web Client Extension |
| Noti | Web Client Notification |
| Anly | Web Client Analysis |
| Rept | Web Client Reporting |
| DB | Database |
| Svcl | Service Layer |
| B1AH | SAP Business One analytics powered by SAP HANA |
| M365 | Microsoft 365 |
| Crpt | Crystal Reports |
