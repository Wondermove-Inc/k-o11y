# K-O11y

[English](README.md) | [한국어](README.ko.md)

Kubernetes Observability Platform built on SigNoz, OpenTelemetry, and Beyla eBPF.

## Components

| Repository | Description |
|------------|-------------|
| [k-o11y-server](https://github.com/Wondermove-Inc/k-o11y-server) | SigNoz fork with ServiceMap, S3 Tiering, SSO |
| [k-o11y-install](https://github.com/Wondermove-Inc/k-o11y-install) | Helm charts, Go CLI tools, DDL |
| [k-o11y-otel-collector](https://github.com/Wondermove-Inc/k-o11y-otel-collector) | OpenTelemetry Collector with CRD Processor |
| [k-o11y-otel-gateway](https://github.com/Wondermove-Inc/k-o11y-otel-gateway) | SigNoz OTel Collector (Gateway) with License Guard |

## Architecture

```
Agent Clusters → OTel DaemonSet/Deployment → OTLP 4317 → Host K-O11y OTel Gateway → ClickHouse
```

- **Host Cluster**: K-O11y Server + ClickHouse (centralized)
- **Agent Clusters**: Data collection via OTel Collector + Beyla eBPF

## Quick Start

See [k-o11y-install](https://github.com/Wondermove-Inc/k-o11y-install) for installation guide.

## License

- Server: [MIT License](https://github.com/Wondermove-Inc/k-o11y-server/blob/main/LICENSE) (SigNoz core)
- OTel components: [Apache License 2.0](https://github.com/Wondermove-Inc/k-o11y-otel-collector/blob/main/LICENSE)

## Maintainers

Built and maintained by [Wondermove](https://wondermove.net).
