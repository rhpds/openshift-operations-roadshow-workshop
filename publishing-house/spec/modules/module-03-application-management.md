# Module 03 — Application Management Basics

### Brief Overview

This module covers the core application lifecycle on OpenShift. Participants deploy a container image, expose it via a TLS-terminated Route, horizontally scale pods, observe self-healing behavior, configure readiness and liveness probes, perform a rolling rollback of a bad deployment, and work with PodDisruptionBudgets. The module concludes by demonstrating how a misconfigured PDB can block cluster upgrades, reinforcing the importance of proper application configuration for cluster operations.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Application Operators
- **Prerequisites:** Completion of Module 01 (basic cluster familiarity)
- **Duration:** 20 minutes

### Learning Objectives

- Deploy a container image and expose it via a TLS-terminated Route
- Scale deployments horizontally and observe self-healing and rolling update behavior
- Configure PodDisruptionBudgets and demonstrate their impact on cluster operations

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Deploy a container image and expose via Route | 4 min |
| 2 | Horizontal scaling and self-healing | 4 min |
| 3 | Readiness/liveness probes and rolling updates | 4 min |
| 4 | Rolling back a bad deployment | 4 min |
| 5 | PodDisruptionBudgets and upgrade impact | 4 min |

### Detailed Steps

1. Create a new project for the application workload
2. Deploy a container image with `oc new-app`
3. Expose the deployment via a TLS-terminated Route
4. Verify the application is accessible and serving traffic
5. Scale the deployment to multiple replicas with `oc scale deployment`
6. Delete a pod and observe self-healing (automatic replacement)
7. Configure readiness and liveness probes on the deployment
8. Trigger a rolling update by setting a new (bad) image with `oc set image`
9. Observe the failed rollout and roll back with `oc rollout undo`
10. Verify the application is healthy after rollback
11. Apply a PodDisruptionBudget YAML manifest with `oc apply`
12. Attempt to drain a node with `oc adm drain` and observe the PDB blocking eviction
13. Discuss how misconfigured PDBs can block cluster upgrades

### Key Takeaways

- OpenShift provides built-in self-healing through ReplicaSet controllers
- Readiness and liveness probes are essential for production workloads
- Rolling updates and rollbacks enable zero-downtime deployment workflows
- PodDisruptionBudgets protect availability but can block node drains and cluster upgrades if misconfigured
- Application lifecycle management is a shared responsibility between developers and platform teams

### Infrastructure Notes

- Requires at least 2 schedulable nodes to demonstrate PDB drain behavior
