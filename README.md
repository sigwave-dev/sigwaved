# Sigwave

> Intelligent Signal Orchestration for Logs, Metrics, and Traces.

**Sigwave** is a flexible, declarative platform for building telemetry pipelines.
It lets you route, enrich, transform, and distribute logs, metrics, and traces — all managed through Kubernetes-native CRDs and visual workflows.

---

## ✨ Features

- 📦 **Modular Pipelines** — Compose routing logic using `Sigflow`, `Sigroute`, and `Sigoutput` resources.
- ⚡ **Real-time Enrichment** — Add context and metadata to any telemetry signal dynamically.
- 🔁 **Declarative Routing** — Define policy-based routes using Kubernetes Custom Resources.
- 📉 **Cost-Aware Destinations** — Route telemetry to different backends based on storage cost, SLA or criticality.
- 🌐 **Multi-tenant Ready** — Namespace-scoped flows for teams, with support for shared `ClusterOutputs`.

---

## 📐 Architecture

```
[ App ] -> [ Sigwave Collector ] -> [ Pipeline: Match + Filter + Enrich + Route ] -> [ Output ]
                                                        |
                                                  [ ClickHouse / Loki / Tempo / Splunk / S3 ]
```

Sigwave leverages the OpenTelemetry Collector as its data plane, and introduces a Kubernetes-native control plane to manage configuration and orchestration.

---

## 🚀 Quick Start

```bash
kubectl apply -f https://sigwave.dev/install.yaml

kubectl apply -f examples/basic-log-pipeline.yaml
```

See [`examples/`](./examples) for more.

---

## 📘 Custom Resources

- [`Sigflow`](./docs/crds/sigflow.md) – Defines a pipeline for a given namespace
- [`Sigroute`](./docs/crds/sigroute.md) – Routing rules inside a flow
- [`Sigoutput`](./docs/crds/sigoutput.md) – Output destinations
- [`Sigparser`](./docs/crds/sigparser.md) – (Optional) Structure and extract fields from raw signals

---

## 🖥️ CLI (Optional)

```bash
sigwave init
sigwave plan -f flow.yaml
sigwave apply -f flow.yaml
```

---

## 🎨 UI

> The Sigwave UI provides a real-time visualization of pipelines, live signals, and CRD structure per namespace.

```
[ Sigwave Dashboard ]
 ├─ Namespaces
 ├─ Active Pipelines
 ├─ Signal Graphs
 └─ Output Routes
```

---

## 📦 Integrations

- ✅ OpenTelemetry Collector
- ✅ Loki, Tempo, ClickHouse, Splunk
- ✅ Kafka, S3, HTTP, OTLP
- ✅ Grafana and Prometheus
- 🧠 Planned: Anomaly detection via ML plugins

---

## 📄 License

[MIT](./LICENSE)

---

## 💬 Community

- Website: [https://sigwave.dev](https://sigwave.dev)
- GitHub Issues: Use for bugs and proposals
- Discord: Coming soon

---

_Designed with focus. Inspired by systems that scale._
