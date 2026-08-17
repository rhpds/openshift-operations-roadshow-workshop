# Module 07 — GitOps - Declarative Cluster Management

### Brief Overview

This module introduces ArgoCD on OpenShift for declarative cluster configuration management. Participants deploy project configuration from a Git repository, simulate configuration drift by manually modifying resources, detect drift through the ArgoCD UI, resync to restore desired state, and enable self-healing to prevent drift automatically. The module demonstrates how GitOps principles apply to cluster operations beyond application deployment.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Cluster Administrators
- **Prerequisites:** Completion of Module 01 (cluster access); basic Git knowledge
- **Duration:** 15 minutes

### Learning Objectives

- Deploy cluster configuration from Git using ArgoCD AppProject and Application resources
- Demonstrate drift detection, manual resync, and self-healing in ArgoCD

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Review the ArgoCD instance and access the UI | 2 min |
| 2 | Deploy project configuration from Git | 4 min |
| 3 | Simulate and detect configuration drift | 4 min |
| 4 | Resync and enable self-healing | 5 min |

### Detailed Steps

1. Access the ArgoCD web UI via its Route
2. Review the pre-installed ArgoCD instance and its configuration
3. Apply an AppProject YAML manifest to define the project scope with `oc apply`
4. Apply an Application YAML manifest pointing to a Git repository containing cluster configuration
5. Observe ArgoCD syncing the configuration and creating resources
6. Verify the deployed resources match the Git-defined desired state
7. Simulate drift by manually patching a ResourceQuota with `oc patch resourcequota`
8. Return to the ArgoCD UI and observe the drift detection (OutOfSync status)
9. Trigger a manual resync from the ArgoCD UI or via `oc patch application`
10. Verify the resource is restored to its Git-defined state
11. Enable self-healing on the Application resource
12. Simulate drift again and observe ArgoCD automatically correcting it
13. Discuss GitOps best practices for cluster configuration management

### Key Takeaways

- ArgoCD provides continuous reconciliation between Git-defined desired state and cluster actual state
- Drift detection alerts operators to unauthorized or accidental configuration changes
- Self-healing automatically reverts drift without manual intervention
- GitOps for cluster configuration provides auditability through Git history
- AppProject resources scope what an Application can deploy and where

### Infrastructure Notes

- OpenShift GitOps operator must be pre-installed
- ArgoCD instance must be accessible via Route
- A Git repository with sample cluster configuration must be available
