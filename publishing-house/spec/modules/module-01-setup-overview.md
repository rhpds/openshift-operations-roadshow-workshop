# Module 01 — Setup & Overview

### Brief Overview

This module introduces the OpenShift Ops Day Roadshow workshop, verifies participant access to the lab environment, and provides a guided tour of built-in OpenShift platform capabilities. Participants confirm cluster connectivity, deploy a quick demo application, and explore core platform features including monitoring, the internal container registry, ingress routing, node management, MachineSets, over-the-air upgrades, and the OperatorHub catalog. This module establishes the baseline understanding of the cluster environment that all subsequent modules build upon.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Security Administrators, Cluster Administrators
- **Prerequisites:** Basic familiarity with Kubernetes concepts and the `oc` CLI
- **Duration:** 20 minutes

### Learning Objectives

- Verify cluster access and connectivity using `oc` CLI commands
- Deploy a sample application and expose it via a TLS-terminated route
- Explore built-in OpenShift platform capabilities including monitoring, registry, ingress, and OperatorHub

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Workshop introduction and environment access | 3 min |
| 2 | Verify cluster connectivity and node status | 3 min |
| 3 | Tour built-in platform capabilities (Prometheus, registry, ingress, MachineSets, upgrades) | 7 min |
| 4 | Deploy a demo application and create a route | 5 min |
| 5 | Explore the web console and OperatorHub | 2 min |

### Detailed Steps

1. Log in to the OpenShift web console using provided credentials
2. Open the web terminal and verify CLI access with `oc whoami` and `oc get nodes`
3. Check the cluster version with `oc get clusterversion`
4. Review built-in monitoring by navigating to the Prometheus dashboard
5. Explore the internal container registry with `oc get imagestreams -n openshift`
6. Examine ingress routes with `oc get routes --all-namespaces`
7. Review node management and MachineSets with `oc get machinesets -n openshift-machine-api`
8. Scale a MachineSet to observe node provisioning with `oc scale machineset`
9. Check available operators with `oc get packagemanifests`
10. Create a new project with `oc new-project`
11. Deploy a sample application with `oc new-app`
12. Expose the application with `oc create route edge`
13. Verify the application is accessible via the route URL
14. Explore the web console overview dashboard

### Key Takeaways

- OpenShift provides integrated monitoring, registry, and ingress out of the box
- MachineSets enable declarative node management and scaling
- The OperatorHub provides a catalog of installable platform extensions
- Over-the-air cluster upgrades are managed through the ClusterVersion API
- The web console and CLI provide complementary interfaces for cluster administration

### Infrastructure Notes

- Requires cluster-admin access for all participants
- Pre-installed operators must be visible in OperatorHub
- Sample application images must be accessible from the cluster (quay.io, registry.access.redhat.com)
