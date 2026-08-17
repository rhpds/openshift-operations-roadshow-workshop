# Module 15 — ACM Multi-Cluster Management

### Brief Overview

This module covers Red Hat Advanced Cluster Management (RHACM) for multi-cluster lifecycle management. Participants create a hosted control plane (HCP) cluster, deploy virtual machines from the RHACM console, configure multi-cluster application deployment using ArgoCD ApplicationSets, and implement GDPR governance policies. The module demonstrates centralized management of multiple OpenShift clusters from a single pane of glass.

### Audience and Time

- **Target personas:** Platform Engineers, Cluster Administrators, Governance/Compliance Engineers
- **Prerequisites:** Completion of Module 01 (cluster access); basic multi-cluster concepts
- **Duration:** 30 minutes

### Learning Objectives

- Create a hosted control plane cluster and deploy workloads across multiple clusters using RHACM
- Implement governance policies for compliance enforcement across managed clusters

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Review the RHACM console and managed clusters | 4 min |
| 2 | Create a hosted control plane (HCP) cluster | 8 min |
| 3 | Deploy VMs from the RHACM console | 5 min |
| 4 | Multi-cluster application deployment with ApplicationSets | 7 min |
| 5 | GDPR governance policies | 6 min |

### Detailed Steps

1. Access the RHACM web console and review the cluster overview
2. Review the existing managed clusters
3. Create a hosted control plane cluster using the RHACM console
4. Wait for the HCP cluster to reach a Ready state
5. Deploy virtual machines to the managed cluster from the RHACM console
6. Verify VM workloads are running on the managed cluster
7. Configure an ArgoCD ApplicationSet for multi-cluster deployment
8. Apply the ApplicationSet to deploy an application across multiple managed clusters with `oc apply`
9. Verify the application is deployed on all target clusters
10. Create a GDPR governance policy using a Policy YAML manifest
11. Apply a Placement resource to target the policy to specific clusters with `oc apply`
12. Observe the policy compliance status in the RHACM console
13. Simulate a policy violation and observe the non-compliant status
14. Remediate the violation and verify compliance is restored

### Key Takeaways

- RHACM provides centralized lifecycle management for multiple OpenShift clusters
- Hosted control planes reduce infrastructure overhead for managed clusters
- ArgoCD ApplicationSets enable declarative multi-cluster application deployment
- Governance policies enforce compliance standards across all managed clusters
- Policy placement rules control which clusters are subject to each policy
- RHACM integrates with OpenShift Virtualization for VM management across clusters

### Infrastructure Notes

- RHACM operator must be pre-installed on the hub cluster
- Sufficient resources must be available for HCP cluster creation
- OpenShift GitOps must be configured for ApplicationSet support
- Governance policies require the Policy Framework to be installed
