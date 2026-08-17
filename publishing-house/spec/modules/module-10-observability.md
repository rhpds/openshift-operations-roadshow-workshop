# Module 10 — Observability & Logging

### Brief Overview

This is the longest module in the workshop, covering all three pillars of observability plus distributed tracing. Participants configure Prometheus for user workload monitoring and custom dashboards, create PrometheusRules for alerting with email notifications via Alertmanager and Mailpit, deploy the Loki logging stack with Vector and S3 storage via ODF, and set up Tempo with OpenTelemetry for distributed tracing. This module provides comprehensive hands-on experience with the full OpenShift observability stack.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Observability Engineers
- **Prerequisites:** Completion of Modules 01-03 (cluster access, application deployed); familiarity with monitoring concepts
- **Duration:** 40 minutes

### Learning Objectives

- Configure Prometheus for user workload monitoring, custom dashboards, and alerting with PrometheusRules
- Deploy the Loki logging stack with Vector and S3 storage for centralized log aggregation
- Implement distributed tracing using Tempo and OpenTelemetry Collector

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Metrics: cluster and node monitoring with `oc adm top` | 5 min |
| 2 | Metrics: enable user workload monitoring and custom dashboards | 7 min |
| 3 | Alerting: PrometheusRules and Alertmanager with Mailpit | 8 min |
| 4 | Logging: deploy LokiStack with Vector and S3 | 10 min |
| 5 | Tracing: deploy Tempo and OpenTelemetry Collector | 10 min |

### Detailed Steps

1. Review cluster resource consumption with `oc adm top nodes`
2. Review pod resource consumption with `oc adm top pods`
3. Explore the built-in Prometheus dashboards in the web console
4. Enable user workload monitoring in the cluster monitoring configuration
5. Deploy a sample application that exposes Prometheus metrics
6. Create a custom Grafana-style dashboard in the OpenShift console
7. Create a PrometheusRule for alerting on a sample metric with `oc apply`
8. Configure Alertmanager to send email notifications
9. Deploy Mailpit as a local email receiver
10. Trigger an alert and verify the email notification arrives in Mailpit
11. Create an S3 bucket for log storage using NooBaa (ODF)
12. Deploy a LokiStack CR for log aggregation with `oc apply`
13. Deploy a ClusterLogForwarder CR to forward logs via Vector with `oc apply`
14. Verify logs are flowing into Loki through the console log viewer
15. Query logs using LogQL in the console
16. Deploy a TempoMonolithic CR for distributed tracing with `oc apply`
17. Deploy an OpenTelemetry Collector to collect and forward traces
18. Deploy a sample instrumented application that generates traces
19. View distributed traces in the Tempo UI
20. Correlate traces with logs and metrics in the observability stack

### Key Takeaways

- OpenShift provides integrated observability across metrics, logging, and tracing
- User workload monitoring enables custom application metrics alongside platform metrics
- PrometheusRules and Alertmanager provide a declarative alerting pipeline
- Loki with Vector provides lightweight, label-based log aggregation at scale
- OpenTelemetry provides vendor-neutral instrumentation for distributed tracing
- The three pillars (metrics, logs, traces) complement each other for root cause analysis

### Infrastructure Notes

- Requires ODF/NooBaa for S3 storage (Loki log storage)
- Loki, Tempo, and OpenTelemetry operators must be pre-installed
- Tempo requires a 10Gi PV for trace storage
- Mailpit must be deployed for email notification testing
