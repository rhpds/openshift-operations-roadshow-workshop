# Module 12 — Virtualization

### Brief Overview

This module covers OpenShift Virtualization for running virtual machines alongside containers on the same platform. Participants provision a RHEL 9 VM using InstanceTypes, observe VMs as pods in the cluster, explore unified monitoring and networking, perform live migration between nodes, clone a VM, and create and restore snapshots. The module demonstrates how OpenShift Virtualization unifies container and VM workloads under a single management plane.

### Audience and Time

- **Target personas:** Platform Engineers, Infrastructure Administrators, Virtualization Administrators
- **Prerequisites:** Completion of Module 01 (cluster access); basic VM concepts
- **Duration:** 25 minutes

### Learning Objectives

- Provision and manage RHEL 9 virtual machines on OpenShift Virtualization using InstanceTypes
- Demonstrate live migration, cloning, and snapshot/restore operations for virtual machines

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Verify OpenShift Virtualization operator status | 2 min |
| 2 | Provision a RHEL 9 VM using InstanceTypes | 5 min |
| 3 | Explore VMs as pods and unified monitoring/networking | 5 min |
| 4 | Live migration between nodes | 5 min |
| 5 | Clone a VM | 4 min |
| 6 | Create and restore a snapshot | 4 min |

### Detailed Steps

1. Verify the OpenShift Virtualization operator is installed with `oc get csv -n openshift-cnv`
2. Review available VirtualMachine InstanceTypes
3. Create a RHEL 9 VirtualMachine using an InstanceType via the web console or YAML
4. Wait for the VM to start and reach Running phase
5. Access the VM console with `virtctl console`
6. Observe the VM running as a pod with `oc get vmi`
7. View VM metrics in the OpenShift monitoring dashboard
8. Verify the VM has network connectivity within the cluster
9. Trigger a live migration of the VM to another node
10. Verify the VM remains accessible during and after migration
11. Clone the running VM to create a copy
12. Verify the cloned VM starts successfully
13. Create a snapshot of the VM
14. Make changes inside the VM (create a file, modify configuration)
15. Restore the VM from the snapshot
16. Verify the VM reverts to its pre-snapshot state

### Key Takeaways

- OpenShift Virtualization runs VMs as first-class citizens alongside containers
- InstanceTypes provide standardized VM sizing similar to cloud instance types
- Live migration enables zero-downtime node maintenance for VM workloads
- VM snapshots provide point-in-time recovery capability
- Unified monitoring and networking eliminate the need for separate VM management tools
- MTV (Migration Toolkit for Virtualization) can migrate VMs from VMware and other hypervisors

### Infrastructure Notes

- OpenShift Virtualization (CNV) operator must be pre-installed
- Cluster nodes must support hardware virtualization
- RHEL 9 VM images must be available (30Gi disk)
- At least 2 schedulable nodes required for live migration
