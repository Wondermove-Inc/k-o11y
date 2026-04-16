# K-O11y

[English](README.md) | [한국어](README.ko.md)

SigNoz, OpenTelemetry, Beyla eBPF 기반의 Kubernetes 관측성 플랫폼.

## 구성 요소

| 저장소 | 설명 |
|--------|------|
| [k-o11y-server](https://github.com/Wondermove-Inc/k-o11y-server) | SigNoz 포크 (ServiceMap, S3 Tiering, SSO) |
| [k-o11y-install](https://github.com/Wondermove-Inc/k-o11y-install) | Helm 차트, Go CLI 도구, DDL |
| [k-o11y-otel-collector](https://github.com/Wondermove-Inc/k-o11y-otel-collector) | CRD Processor 포함 OpenTelemetry Collector |
| [k-o11y-otel-gateway](https://github.com/Wondermove-Inc/k-o11y-otel-gateway) | License Guard 포함 SigNoz OTel Collector (Gateway) |

## 아키텍처

```
Agent 클러스터 → OTel DaemonSet/Deployment → OTLP 4317 → Host K-O11y OTel Gateway → ClickHouse
```

- **Host 클러스터**: K-O11y Server + ClickHouse (중앙집중)
- **Agent 클러스터**: OTel Collector + Beyla eBPF로 데이터 수집

## 빠른 시작

설치 가이드는 [k-o11y-install](https://github.com/Wondermove-Inc/k-o11y-install)을 참조하세요.

## 라이선스

- Server: [MIT License](https://github.com/Wondermove-Inc/k-o11y-server/blob/main/LICENSE) (SigNoz 코어)
- OTel 컴포넌트: [Apache License 2.0](https://github.com/Wondermove-Inc/k-o11y-otel-collector/blob/main/LICENSE)

## 관리자

[Wondermove](https://wondermove.net)가 개발 및 관리합니다.
