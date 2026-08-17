# Module 11 — Performance Tuning

### Brief Overview

This module covers application performance tuning on OpenShift using vertical and horizontal pod autoscaling. Participants diagnose an over-provisioned application, use VPA recommendations to right-size resource requests and limits, configure HPA for automatic horizontal scaling under load, and perform capacity planning. The module connects observability data from Module 10 to actionable performance optimizations.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Application Operators
- **Prerequisites:** Completion of Modules 01-03 (application management basics); Module 10 recommended (observability context)
- **Duration:** 20 minutes

### Learning Objectives

- Analyze resource consumption and implement VPA recommendations to right-size application workloads
- Configure HPA for automatic horizontal scaling and verify scaling behavior under load

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Diagnose an over-provisioned application | 4 min |
| 2 | Review VPA recommendations and right-size | 5 min |
| 3 | Configure HPA for horizontal autoscaling | 5 min |
| 4 | Generate load and observe scaling behavior | 4 min |
| 5 | Capacity planning discussion | 2 min |

### Detailed Steps

1. Deploy an application with excessively large resource requests
2. Review actual resource consumption with `oc adm top pod`
3. Compare requested resources to actual usage to identify over-provisioning
4. Deploy a VerticalPodAutoscaler resource for the application
5. Review VPA recommendations with `oc get vpa`
6. Apply the VPA-recommended resource requests and limits to the deployment
7. Verify the application runs with right-sized resources
8. Configure an HPA for the deployment with `oc autoscale deployment`
9. Set target CPU utilization threshold
10. Generate load against the application with `oc run` (load generator pod)
11. Observe HPA scaling up replicas in response to increased CPU utilization
12. Stop the load generator and observe HPA scaling down
13. Discuss capacity planning strategies using VPA and HPA together

### Key Takeaways

- Over-provisioned applications waste cluster resources and increase costs
- VPA provides data-driven recommendations for right-sizing resource requests
- HPA scales horizontally based on real-time metrics (CPU, memory, custom metrics)
- VPA and HPA serve complementary purposes and can be combined with careful configuration
- Capacity planning requires ongoing monitoring and periodic right-sizing reviews

### Infrastructure Notes

- VPA operator must be pre-installed
- Metrics Server must be available for HPA CPU-based scaling
