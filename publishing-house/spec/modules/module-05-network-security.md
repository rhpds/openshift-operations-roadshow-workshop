# Module 05 — Network Security

### Brief Overview

This module covers OVN-Kubernetes networking and network security policies on OpenShift. Participants implement a deny-all NetworkPolicy, configure cross-namespace traffic using label selectors, apply AdminNetworkPolicy for cluster-wide rules, configure EgressFirewall to restrict outbound traffic, and set up EgressIP for source IP management. The module also covers DNS service discovery within the cluster.

### Audience and Time

- **Target personas:** Platform Engineers, Security Administrators, Network Administrators
- **Prerequisites:** Completion of Module 03 (application deployed); basic understanding of Kubernetes networking
- **Duration:** 15 minutes

### Learning Objectives

- Implement NetworkPolicy and AdminNetworkPolicy to control ingress and cross-namespace traffic
- Configure EgressFirewall and EgressIP for outbound traffic control and source IP management

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Apply a deny-all NetworkPolicy | 3 min |
| 2 | Allow cross-namespace traffic with label selectors | 3 min |
| 3 | AdminNetworkPolicy for cluster-wide rules | 3 min |
| 4 | EgressFirewall and EgressIP configuration | 4 min |
| 5 | DNS service discovery verification | 2 min |

### Detailed Steps

1. Deploy test applications in multiple namespaces
2. Apply a deny-all NetworkPolicy with `oc apply`
3. Verify that all ingress traffic to the namespace is blocked
4. Create a NetworkPolicy allowing traffic from a specific namespace using label selectors
5. Label the source namespace with `oc label namespace`
6. Verify cross-namespace traffic is now permitted
7. Apply an AdminNetworkPolicy for cluster-wide traffic rules
8. Verify AdminNetworkPolicy enforcement across namespaces
9. Create an EgressFirewall to restrict outbound traffic with `oc apply`
10. Test that blocked egress destinations are unreachable
11. Configure EgressIP for a namespace
12. Verify the source IP of outbound traffic matches the configured EgressIP
13. Test DNS service discovery between namespaces using fully qualified service names

### Key Takeaways

- OVN-Kubernetes provides a robust network policy engine for OpenShift
- NetworkPolicy operates at the namespace level; AdminNetworkPolicy provides cluster-wide enforcement
- A deny-all policy is a best practice starting point for network segmentation
- EgressFirewall controls which external destinations workloads can reach
- EgressIP provides deterministic source IPs for firewall allow-listing
- DNS service discovery enables cross-namespace communication using predictable names

### Infrastructure Notes

- OVN-Kubernetes must be the cluster CNI (default for OpenShift 4.20+)
- AdminNetworkPolicy requires OVN-Kubernetes with the AdminNetworkPolicy feature enabled
