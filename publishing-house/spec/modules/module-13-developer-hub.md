# Module 13 — Developer Hub

### Brief Overview

This module covers Red Hat Developer Hub (RHDH), the enterprise Backstage distribution for OpenShift. Participants explore the software catalog with live Kubernetes data, use golden path templates for self-service provisioning, troubleshoot a support ticket scenario using the catalog, and enable Prometheus monitoring for the RHDH instance. The module demonstrates how RHDH provides a unified developer portal that integrates with the broader OpenShift ecosystem.

### Audience and Time

- **Target personas:** Platform Engineers, Developer Experience leads, SREs
- **Prerequisites:** Completion of Module 01 (cluster access); Modules 07, 10 recommended (GitOps, observability context)
- **Duration:** 30 minutes

### Learning Objectives

- Explore the Red Hat Developer Hub software catalog with live Kubernetes data and golden path templates
- Configure Prometheus monitoring for Red Hat Developer Hub and use catalog data for operational troubleshooting

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Review the RHDH instance and software catalog | 5 min |
| 2 | Explore live Kubernetes data in catalog components | 5 min |
| 3 | Use a golden path template for self-service provisioning | 8 min |
| 4 | Troubleshoot a support ticket using catalog data | 7 min |
| 5 | Enable Prometheus monitoring for RHDH | 5 min |

### Detailed Steps

1. Verify the Backstage instance is running with `oc get backstage`
2. Access the Developer Hub web UI via its Route
3. Browse the software catalog and explore registered components
4. View live Kubernetes data (pods, deployments, services) for a catalog component
5. Explore the component's CI/CD pipeline information (Tekton/ArgoCD)
6. Navigate to a golden path template in the catalog
7. Use the template to provision a new application with self-service
8. Verify the provisioned resources are created in the cluster
9. Review a simulated support ticket referencing a catalog component
10. Use the catalog to identify the component owner, dependencies, and runtime status
11. Diagnose the issue using the live Kubernetes data in the catalog
12. Review the RHDH ConfigMap with `oc get configmap`
13. Patch the Backstage instance to enable Prometheus monitoring with `oc patch backstage`
14. Verify the ServiceMonitor is created with `oc get servicemonitor`
15. View RHDH metrics in the Prometheus dashboard

### Key Takeaways

- Red Hat Developer Hub provides a unified portal for service catalog, documentation, and self-service
- Live Kubernetes data in the catalog reduces context switching for developers and operators
- Golden path templates standardize application provisioning and reduce onboarding time
- The software catalog serves as a service directory for operational troubleshooting
- Prometheus integration provides observability for the Developer Hub platform itself

### Infrastructure Notes

- RHDH (Backstage) operator must be pre-installed with a configured instance
- ArgoCD and Tekton integrations must be configured for full catalog functionality
- Sample catalog components must be pre-registered
