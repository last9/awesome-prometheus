# Awesome Prometheus [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Open-source systems monitoring and alerting toolkit.

[Prometheus](https://prometheus.io/) is an open-source metrics and alerting system, part of the CNCF. This list covers PromQL, alerting, exporters, cardinality management, and scaling.

## Contents

- [Official Resources](#official-resources)
- [Getting Started](#getting-started)
- [Metric Types](#metric-types)
- [PromQL](#promql)
- [Alerting](#alerting)
- [Recording Rules](#recording-rules)
- [Exporters](#exporters)
- [Cardinality and Storage](#cardinality-and-storage)
- [Scaling and Federation](#scaling-and-federation)
- [Kubernetes](#kubernetes)
- [Dashboards and Visualization](#dashboards-and-visualization)
- [OpenTelemetry Integration](#opentelemetry-integration)
- [Tools](#tools)
- [Alternatives and Compatibility](#alternatives-and-compatibility)
- [Books](#books)

## Official Resources

- [Prometheus Documentation](https://prometheus.io/docs/) - Full reference for installation, configuration, querying, and alerting.
- [Prometheus GitHub](https://github.com/prometheus/prometheus) - Source code and issue tracker.
- [Prometheus Community](https://prometheus.io/community/) - Mailing list, Slack, and governance info.
- [CNCF Prometheus Project](https://www.cncf.io/projects/prometheus/) - Project maturity, security contacts, and CNCF overview.

## Getting Started

- [Getting Started Guide](https://prometheus.io/docs/prometheus/latest/getting_started/) - Official walkthrough: install Prometheus, configure scrape targets, run your first query.
- [First Steps with Prometheus](https://prometheus.io/docs/introduction/first_steps/) - Covers scrape config, targets, and basic PromQL.
- [Robust Perception Blog](https://www.robustperception.io/blog) - Written by Prometheus core maintainers. Covers edge cases and internals that the official docs skip.
- [Prometheus: Up & Running](https://www.oreilly.com/library/view/prometheus-up/9781098131135/) - O'Reilly book by Julien Pivotto and Brian Brazil. The standard reference for production setups.

## Metric Types

- [Prometheus Metric Types Deep Dive](https://last9.io/blog/prometheus-metrics-types-a-deep-dive/) - Counters, gauges, histograms, and summaries with PromQL examples for each.
- [Counters vs Gauges in Prometheus](https://last9.io/blog/prometheus-gauges-vs-counters/) - When to use each type and common mistakes.
- [Histogram Buckets in Prometheus](https://last9.io/blog/histogram-buckets-in-prometheus/) - How bucket boundaries work and how to use `histogram_quantile()` correctly.
- [Metric Types Reference](https://prometheus.io/docs/concepts/metric_types/) - Official reference for counter, gauge, histogram, and summary semantics.

## PromQL

- [PromQL Cheat Sheet](https://last9.io/blog/promql-cheat-sheet/) - Common queries organized by use case: aggregations, label filtering, SLO tracking, and capacity planning.
- [PromQL for Beginners](https://last9.io/blog/promql-for-beginners-getting-started-with-prometheus-query-language/) - Instant vectors, range vectors, and how metric types affect query behavior.
- [Prometheus Query Examples](https://last9.io/blog/prometheus-query-examples/) - Practical `rate()`, `histogram_quantile()`, and error budget queries with explanations.
- [rate() vs irate() vs increase()](https://last9.io/blog/prometheus-rate-function/) - When to use each function and how time window selection affects results.
- [PromQL Query Language Reference](https://prometheus.io/docs/prometheus/latest/querying/basics/) - Official syntax and operator reference.
- [PromQL Macros](https://last9.io/blog/standardize-promql-with-macros/) - How to define reusable PromQL expressions to keep queries consistent across teams.

## Alerting

- [Prometheus Alerting Examples](https://last9.io/blog/prometheus-alerting-examples/) - Alerting rules for common infrastructure and application scenarios.
- [Prometheus Alertmanager Guide](https://last9.io/blog/prometheus-alertmanager/) - Routing, inhibition, silencing, and integrating with PagerDuty and Slack.
- [Awesome Prometheus Alerts](https://github.com/samber/awesome-prometheus-alerts) - Copy-paste alert rules for Kubernetes, databases, message queues, and cloud providers. Community-maintained.
- [Alerting Rules Reference](https://prometheus.io/docs/prometheus/latest/configuration/alerting_rules/) - Official docs for writing and configuring alert rules.
- [Alertmanager Reference](https://prometheus.io/docs/alerting/latest/alertmanager/) - Configuration reference for routing trees, receivers, and inhibition rules.

## Recording Rules

- [Prometheus Recording Rules](https://last9.io/blog/prometheus-recording-rules/) - How to precompute expensive queries and organize rules for maintainability.
- [Recording Rules Reference](https://prometheus.io/docs/prometheus/latest/configuration/recording_rules/) - Official syntax and naming conventions.
- [Metric and Label Naming](https://prometheus.io/docs/practices/naming/) - Official naming guide including conventions for recording rule metrics.

## Exporters

- [last9/prometheus-exporters](https://github.com/last9/prometheus-exporters) - Curated list of standard Prometheus exporters organized by category.
- [Official Exporters List](https://prometheus.io/docs/instrumenting/exporters/) - Exporters maintained by the Prometheus project and well-known community exporters.
- [node_exporter](https://github.com/prometheus/node_exporter) - Hardware and OS metrics for Linux and macOS hosts.
- [blackbox_exporter](https://github.com/prometheus/blackbox_exporter) - Probes HTTP, HTTPS, DNS, TCP, and ICMP endpoints.
- [mysqld_exporter](https://github.com/prometheus/mysqld_exporter) - MySQL server metrics.
- [postgres_exporter](https://github.com/prometheus-community/postgres_exporter) - PostgreSQL metrics.
- [Writing Exporters Guide](https://prometheus.io/docs/instrumenting/writing_exporters/) - Official guidance on building a custom exporter correctly.

## Cardinality and Storage

- [Managing High Cardinality in Prometheus](https://last9.io/blog/how-to-manage-high-cardinality-metrics-in-prometheus/) - How to identify and fix cardinality problems before they cause OOM crashes or slow queries.
- [Downsampling and Aggregating Prometheus Metrics](https://last9.io/blog/downsampling-aggregating-metrics-in-prometheus-practical-strategies-to-manage-cardinality-and-query-performance/) - Reducing storage cost and query overhead with recording rules and remote storage.
- [Troubleshooting Prometheus Pitfalls](https://last9.io/blog/troubleshooting-common-prometheus-pitfalls-cardinality-resource-utilization-and-storage-challenges/) - Diagnosing cardinality, memory, and storage issues in production.
- [Storage Reference](https://prometheus.io/docs/prometheus/latest/storage/) - Official storage model, TSDB format, retention, and compaction.

## Scaling and Federation

- [Scaling Prometheus](https://last9.io/blog/scaling-prometheus-tips-tricks-and-proven-strategies/) - Sharding, federation, and remote storage patterns for high-traffic environments.
- [Federation Reference](https://prometheus.io/docs/prometheus/latest/federation/) - Official docs for scraping one Prometheus from another.
- [Thanos](https://github.com/thanos-io/thanos) - Extends Prometheus with high availability, unlimited long-term storage, and global query view.
- [VictoriaMetrics](https://github.com/VictoriaMetrics/VictoriaMetrics) - Drop-in Prometheus-compatible backend with lower resource usage.
- [Cortex](https://github.com/cortexproject/cortex) - Horizontally scalable multi-tenant Prometheus backend.
- [Grafana Mimir](https://github.com/grafana/mimir) - Scalable Prometheus backend with object storage support.

## Kubernetes

- [kube-prometheus-stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack) - Helm chart that bundles Prometheus, Alertmanager, Grafana, and kube-state-metrics.
- [prometheus-operator](https://github.com/prometheus-operator/prometheus-operator) - Manages Prometheus instances and rules via Kubernetes CRDs.
- [kube-state-metrics](https://github.com/kubernetes/kube-state-metrics) - Exposes Kubernetes object state (pods, deployments, nodes) as Prometheus metrics.
- [Kubernetes Monitoring with Prometheus](https://prometheus.io/docs/guides/file-sd/) - Official guide for service discovery in Kubernetes environments.

## Dashboards and Visualization

- [Prometheus and Grafana](https://last9.io/blog/prometheus-and-grafana/) - Connecting Prometheus to Grafana, building dashboards, and writing PromQL panel queries.
- [Grafana](https://github.com/grafana/grafana) - The standard open-source visualization layer for Prometheus.
- [Grafana Dashboard Library](https://grafana.com/grafana/dashboards/) - Community dashboards for common exporters and stacks.
- [Prometheus Console Templates](https://prometheus.io/docs/visualization/consoles/) - Built-in templating for lightweight dashboards served directly by Prometheus.

## OpenTelemetry Integration

- [OpenTelemetry Prometheus Exporter](https://opentelemetry.io/docs/specs/otel/metrics/sdk_exporters/prometheus/) - Export OpenTelemetry metrics in Prometheus format.
- [OTEL Collector Prometheus Receiver](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/receiver/prometheusreceiver) - Scrape Prometheus endpoints from the OpenTelemetry Collector.
- [Bridging Prometheus and OpenTelemetry](https://prometheus.io/docs/guides/opentelemetry/) - Official guide for running Prometheus alongside an OpenTelemetry stack.

## Tools

- [promtool](https://prometheus.io/docs/prometheus/latest/command-line/promtool/) - Official CLI for validating config files, unit-testing rules, and running ad-hoc queries.
- [prom-label-proxy](https://github.com/prometheus-community/prom-label-proxy) - Enforces label matchers on incoming PromQL queries. Useful for multi-tenant setups.
- [promlens](https://promlens.com/) - Visual PromQL query builder and expression explainer.
- [mixtool](https://github.com/monitoring-mixins/mixtool) - CLI for working with Jsonnet monitoring mixins.
- [awesome-lint](https://github.com/sindresorhus/awesome-lint) - Linter for awesome lists. Run before submitting a PR.

## Alternatives and Compatibility

- [Prometheus Alternatives](https://last9.io/blog/prometheus-alternatives/) - Comparison of Grafana Mimir, Datadog, InfluxDB, Graphite, and Zabbix against Prometheus.
- [OpenMetrics](https://github.com/OpenObservability/OpenMetrics) - CNCF standard that extends the Prometheus text exposition format.
- [Last9](https://last9.io/metrics/) - Managed observability platform with Prometheus and OpenTelemetry remote write compatibility.

## Books

- [Prometheus: Up & Running, 2nd Ed.](https://www.oreilly.com/library/view/prometheus-up/9781098131135/) - Julien Pivotto and Brian Brazil. Covers production setup, PromQL, alerting, and scaling.

---

## Contributing

Contributions are welcome. Read the [contributing guidelines](CONTRIBUTING.md) first.
