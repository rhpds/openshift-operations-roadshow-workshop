# Module 02 — Installation & Verification

### Brief Overview

This module covers post-installation verification of an OpenShift cluster. Participants perform systematic health checks across ClusterOperators, cluster version and update channels, MachineConfigPools, networking connectivity, dynamic storage provisioning, and etcd health metrics. The module also provides an overview of OpenShift installation methods (IPI, UPI, Assisted, Agent-based) for context on how the lab cluster was provisioned.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Cluster Administrators
- **Prerequisites:** Completion of Module 01 (cluster access verified)
- **Duration:** 10 minutes

### Learning Objectives

- Verify ClusterOperator health and diagnose degraded conditions
- Verify cluster version, update channels, and MachineConfigPool status
- Validate networking connectivity, dynamic storage provisioning, and etcd health metrics

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | ClusterOperator health checks | 3 min |
| 2 | Cluster version, update channels, and MachineConfigPools | 2 min |
| 3 | Networking and storage verification | 3 min |
| 4 | Etcd health metrics and installation methods overview | 2 min |

### Detailed Steps

1. List all ClusterOperators with `oc get clusteroperators`
2. Inspect a specific ClusterOperator for conditions with `oc describe clusteroperator <name>`
3. Check the cluster version and available updates with `oc get clusterversion` and `oc adm upgrade`
4. Review MachineConfigPool status with `oc get machineconfigpool`
5. Verify networking connectivity by creating a test pod and confirming DNS resolution
6. Test dynamic storage provisioning by applying a PVC YAML manifest
7. Verify the PVC binds successfully and a pod can mount the volume
8. Check etcd health metrics via the Prometheus dashboard
9. Review the different OpenShift installation methods (IPI, UPI, Assisted, Agent-based)

### Key Takeaways

- Post-installation verification is a critical step before handing a cluster to workloads
- ClusterOperator status provides a single view of platform component health
- MachineConfigPools manage OS-level configuration across node groups
- Dynamic storage provisioning confirms the storage subsystem is operational
- Etcd health is foundational to cluster reliability

### Infrastructure Notes

- Requires a StorageClass with dynamic provisioning (ODF/Ceph RBD)
- Prometheus must be accessible for etcd metrics review
