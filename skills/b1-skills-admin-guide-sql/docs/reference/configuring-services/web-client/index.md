# Web Client

## [Setting the Default Browser with Group Policy](default-browser-group-policy.md)
Use when: setting Chrome or Firefox as default browser for the Web client; domain-joined Windows devices; per-machine default browser; SAP Companion CORS error.
Terms: Google Chrome, Mozilla Firefox, `DefaultAssociations`, `ChromeHTML`, `FirefoxHTML`, `Association Identifier`, *Set a default associations configuration file*, Group Policy, *Default apps*, *Web browser*, SAP Companion, CORS, SAP Note 3702859, 10.0 FP 2602

## [OpenTelemetry for the Web Client: Enabling, Data Collected, Configuration](opentelemetry-setup.md)
Use when: enabling OpenTelemetry or local performance logging; environment variables and defaults; which traces, metrics and logs are collected; recommended settings; service abbreviations.
Terms: `PERF_ANA`, `log`, `otel`, `all`, `PERFLOGGING_LEVEL`, `DEBUG`, `INFO`, `OTEL_EXPORTER_ENDPOINT`, `http://localhost:4317`, `http://localhost:4318`, `OTEL_EXPORTER_PROTOCOL`, `grpc`, `http/protobuf`, `OTEL_TRACES_SAMPLER`, `always_on`, `always_off`, `traceidratio`, `OTEL_TRACES_SAMPLER_ARG`, `OTEL_METRIC_INTERVAL_SECONDS`, OtelLogAppender, `http.server.request.count`, `http.server.error.count`, `http.server.request.duration`, `process.cpu.usage`, `jvm.memory.used`, `X-B1-CorrelationId`, `X-B1-SpanId`, Gate, Auth, Tcli, Extn, Noti, Anly, Rept, Svcl, B1AH, M365, Crpt, 30 days traces, 90 days metrics
Sections: [Enabling](opentelemetry-setup.md#enabling-opentelemetry) · [Data collected](opentelemetry-setup.md#telemetry-data-collected-for-analysis) · [Recommended configuration](opentelemetry-setup.md#recommended-configuration) · [Service abbreviations](opentelemetry-setup.md#additional-information)

## [Using OpenTelemetry to Address Performance Issues](opentelemetry-performance-issues.md)
Use when: finding the trace ID in the Web client; viewing traces, metrics and logs in Grafana; local log vs OTEL output mode.
Terms: Grafana, *Explore*, Jaeger, Prometheus, Loki, `X-B1-CorrelationId`, trace ID, developer tools, `http_server_request_duration`, `jvm_memory_used`, `process_cpu_usage`, local log, OpenTelemetry Collector
Not here: exporting data for an SAP Support incident → [opentelemetry-collecting-and-exporting](opentelemetry-collecting-and-exporting.md)

## [Collecting and Exporting Telemetry Data for Performance Analysis](opentelemetry-collecting-and-exporting.md)
Use when: reporting a performance issue to SAP Support; exporting Jaeger trace, Loki logs and Prometheus metrics; files to attach; no trace found for a correlation ID.
Terms: correlation ID, `X-B1-CorrelationId`, `b1.correlation_id=<correlationId>`, `F12`, *Find Traces*, `http://<host>:16686`, `/api/traces/`, `trace-<correlationId>-<YYYYMMDD>.json`, `logs-<correlationId>-<YYYYMMDD>.txt`, `{job=~"b1-webclient.*"}`, logQL, `query_range`, `http_server_request_duration_seconds_bucket`, port `9090`, `14250`, `14268`, `PERF_ANA`, time range UTC
Sections: [Procedure](opentelemetry-collecting-and-exporting.md#procedure) · [Information to attach](opentelemetry-collecting-and-exporting.md#information-to-attach-to-the-support-incident) · [Troubleshooting](opentelemetry-collecting-and-exporting.md#troubleshooting)
