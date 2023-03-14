# Monitoring & Observability

Observability is built upon three pillars: Metrics, Logs, and Traces (the "three pillars of observability").

## The Three Pillars

### 1. Metrics
Quantitative measurements of system health and performance over time.
*   **System Metrics:** CPU usage, RAM utilization, network throughput.
*   **App Metrics:** Request latency, HTTP error rate, active database connections.
*   *Tools:* Prometheus, Datadog.

### 2. Logs
Structured text records of events that occur within the system, detailing specific request parameters, errors, and flows.
*   *Tools:* ELK Stack (Elasticsearch, Logstash, Kibana), Grafana Loki.

### 3. Traces
End-to-end lifecycle representation of a request as it travels through a distributed system.
*   *Tools:* OpenTelemetry, Jaeger.

## Grafana & Prometheus Integration
Prometheus scrapes metric endpoints (such as `/metrics`), stores the values in a time-series database, and Grafana queries Prometheus to render charts, heatmaps, and dashboard panels.
