// go: downgraded go.opentelemetry.io/collector v0.74.0 => v0.67.0
// go: downgraded go.opentelemetry.io/collector/component v0.74.0 => v0.67.0
go install go.opentelemetry.io/collector/cmd/builder@v0.67.0

go run go.opentelemetry.io/collector/cmd/builder@v0.67.0 --config=builder-config.yaml

./otel-collector/otel-collector --config ./otel-collector-config.yaml
2023-04-04T15:22:36.622+0100    info    service/telemetry.go:111        Setting up own telemetry...
2023-04-04T15:22:36.623+0100    info    service/telemetry.go:141        Serving Prometheus metrics      {"address": ":8888", "level": "Basic"}
2023-04-04T15:22:36.623+0100    info    components/components.go:30     Development component. May change in the future.        {"kind": "exporter", "data_type": "traces", "name": "logging", "stability": "Development"}
2023-04-04T15:22:36.623+0100    info    service/service.go:88   Starting otel-collector...      {"Version": "1.0.0", "NumCPU": 12}
2023-04-04T15:22:36.623+0100    info    extensions/extensions.go:42     Starting extensions...
2023-04-04T15:22:36.623+0100    info    service/pipelines.go:76 Starting exporters...
2023-04-04T15:22:36.623+0100    info    service/pipelines.go:80 Exporter is starting... {"kind": "exporter", "data_type": "traces", "name": "logging"}
2023-04-04T15:22:36.623+0100    info    service/pipelines.go:84 Exporter started.       {"kind": "exporter", "data_type": "traces", "name": "logging"}
2023-04-04T15:22:36.623+0100    info    service/pipelines.go:88 Starting processors...
2023-04-04T15:22:36.623+0100    info    service/pipelines.go:100        Starting receivers...
2023-04-04T15:22:36.623+0100    info    service/pipelines.go:104        Receiver is starting... {"kind": "receiver", "name": "otlp", "pipeline": "traces"}
2023-04-04T15:22:36.623+0100    warn    internal/warning.go:51  Using the 0.0.0.0 address exposes this server to every network interface, which may facilitate Denial of Service attacks        {"kind": "receiver", "name": "otlp", "pipeline": "traces", "documentation": "https://github.com/open-telemetry/opentelemetry-collector/blob/main/docs/security-best-practices.md#safeguards-against-denial-of-service-attacks"}
2023-04-04T15:22:36.623+0100    info    otlpreceiver@v0.67.0/otlp.go:72 Starting GRPC server    {"kind": "receiver", "name": "otlp", "pipeline": "traces", "endpoint": "0.0.0.0:4317"}
2023-04-04T15:22:36.623+0100    warn    internal/warning.go:51  Using the 0.0.0.0 address exposes this server to every network interface, which may facilitate Denial of Service attacks        {"kind": "receiver", "name": "otlp", "pipeline": "traces", "documentation": "https://github.com/open-telemetry/opentelemetry-collector/blob/main/docs/security-best-practices.md#safeguards-against-denial-of-service-attacks"}
2023-04-04T15:22:36.624+0100    info    otlpreceiver@v0.67.0/otlp.go:90 Starting HTTP server    {"kind": "receiver", "name": "otlp", "pipeline": "traces", "endpoint": "0.0.0.0:4318"}
2023-04-04T15:22:36.624+0100    info    service/pipelines.go:108        Receiver started.       {"kind": "receiver", "name": "otlp", "pipeline": "traces"}
2023-04-04T15:22:36.624+0100    info    service/service.go:105  Everything is ready. Begin running and processing data.


