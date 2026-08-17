# OpenShift Ops Day Roadshow

## Overview

This is a hands-on operations workshop covering the full breadth of Red Hat OpenShift Container Platform administration. Participants work through 18 modules spanning cluster verification, application lifecycle management, networking, security, identity management, observability, virtualization, multi-cluster management, and developer experience tooling. Each participant receives a dedicated OpenShift 4.20+ compact cluster with pre-installed operators and works through CLI-driven exercises that configure, deploy, troubleshoot, and secure production-like workloads.

## Target Audience

- **Role:** Platform Engineers, Site Reliability Engineers (SREs), Security Administrators, OpenShift Cluster Administrators
- **Experience level:** Intermediate to Advanced
- **What they already know:** Basic Kubernetes concepts (pods, deployments, services), CLI comfort with `oc`/`kubectl`, networking fundamentals (TLS, DNS, HTTP), authentication/authorization concepts, container basics
- **What they don't know:** OpenShift-specific operational patterns including advanced ingress configuration, OVN-Kubernetes network policies, ArgoCD-based GitOps for cluster configuration, LDAP/OIDC identity provider integration, full-stack observability with Prometheus/Loki/Tempo, OpenShift Virtualization lifecycle management, RHACM multi-cluster governance, RHACS compliance scanning, and zero-trust workload identity

## Prerequisites

- Cluster administrator access to a Red Hat OpenShift Container Platform 4.20+ cluster
- Working knowledge of Kubernetes primitives (pods, deployments, services, namespaces)
- Comfort with the `oc` CLI and YAML manifests
- Basic understanding of TLS, DNS, and HTTP networking concepts
- Familiarity with container images and registries
- These prerequisites cannot be automatically validated; they are assumed based on participant role

## Learning Objectives

1. Verify post-installation cluster health including ClusterOperators, MachineConfigPools, networking, storage provisioning, and etcd metrics
2. Deploy and scale applications with self-healing, rolling updates, readiness/liveness probes, and PodDisruptionBudgets
3. Configure ingress routing with TLS termination, HSTS headers, and rate limiting via the OpenShift Ingress Controller
4. Implement network security using NetworkPolicy, AdminNetworkPolicy, EgressFirewall, and EgressIP on OVN-Kubernetes
5. Troubleshoot common pod failures including ImagePullBackOff, CrashLoopBackOff, resource constraints, and SCC violations
6. Deploy declarative cluster configuration using ArgoCD with drift detection and self-healing
7. Integrate LDAP and OIDC identity providers with group sync and role-based access control
8. Configure full-stack observability across metrics, alerting, logging, and distributed tracing using Prometheus, Alertmanager, Loki, Vector, Tempo, and OpenTelemetry
9. Implement horizontal and vertical pod autoscaling with capacity planning based on VPA recommendations
10. Provision and manage virtual machines on OpenShift Virtualization with live migration, cloning, and snapshots
11. Manage multi-cluster environments using RHACM with hosted control planes, ArgoCD ApplicationSets, and governance policies
12. Secure workloads using RHACS compliance scanning, secrets management with HashiCorp Vault and External Secrets Operator, and SPIFFE/SPIRE zero-trust workload identity

## Content Type

Lab (hands-on)

## Products & Technologies

- Red Hat OpenShift Container Platform (4.20+)
- Red Hat Advanced Cluster Security (RHACS)
- Red Hat Advanced Cluster Management (RHACM)
- Red Hat Developer Hub (RHDH)
- Red Hat OpenShift GitOps (ArgoCD)
- Red Hat OpenShift Virtualization (KubeVirt)
- Red Hat OpenShift Data Foundation (ODF/NooBaa)
- Red Hat build of Keycloak (RHBK)
- Red Hat Enterprise Linux (RHEL 9) -- for VMs
- OpenShift Lightspeed (OLS)
- Zero Trust Workload Identity Manager (ZTWIM/SPIRE)
- Prometheus / Alertmanager
- Loki / Vector (Cluster Logging)
- Tempo / Red Hat build of OpenTelemetry
- OVN-Kubernetes / CoreDNS
- HAProxy (Ingress Controller)
- HashiCorp Vault
- External Secrets Operator (ESO)
- Helm
- LDAP (JumpCloud)
- Azure OpenAI (GPT-4)
- PostgreSQL
- Mailpit

## Module Map

| Module | Title | Duration |
|--------|-------|----------|
| 1 | Setup & Overview | 20 min |
| 2 | Installation & Verification | 10 min |
| 3 | Application Management Basics | 20 min |
| 4 | Ingress & Load Balancing | 25 min |
| 5 | Network Security | 15 min |
| 6 | Debugging & Troubleshooting | 15 min |
| 7 | GitOps - Declarative Cluster Management | 15 min |
| 8 | Identity - LDAP | 20 min |
| 9 | Identity - OIDC | 20 min |
| 10 | Observability & Logging | 40 min |
| 11 | Performance Tuning | 20 min |
| 12 | Virtualization | 25 min |
| 13 | Developer Hub | 30 min |
| 14 | Lightspeed | 20 min |
| 15 | ACM Multi-Cluster Management | 30 min |
| 16 | Advanced Cluster Security | 20 min |
| 17 | Secrets Management | 25 min |
| 18 | Zero-Trust Workload Identity Manager | 20 min |
| 19 | Wrap Up | 5 min |
| -- | **Total hands-on** | **390 min** |
| -- | **Total lab** | **~6.5 hours** |

## Difficulty Level

Intermediate

## Environment

**Learner view:** Each participant starts with a dedicated OpenShift 4.20+ compact cluster (3 nodes serving as both control plane and workers). The cluster has pre-installed operators including OpenShift Virtualization, RHACS, RHACM, OpenShift GitOps, Developer Hub, Lightspeed, Loki, Tempo, OpenTelemetry, Compliance Operator, VPA, Keycloak, ZTWIM, and ODF. Participants access the cluster via a web terminal and the OpenShift web console with cluster-admin credentials. Several demo applications and intentionally broken microservices are deployed during the exercises.

**Automation needed:** Yes

Pre-provisioned by automation:
- OpenShift 4.20+ cluster with compact 3-node topology
- All required operators installed and configured (CNV, RHACS, RHACM, GitOps, RHDH, Lightspeed, Loki, Tempo, OTel, Compliance, VPA, Keycloak, ZTWIM, ODF)
- JumpCloud LDAP integration credentials
- Azure OpenAI API credentials for Lightspeed
- HashiCorp Vault Helm chart accessible
- Sample application images available via quay.io and registry.access.redhat.com

## Infrastructure Requirements

- **Cloud provider:** CNV (default)
- **Cluster type:** Multinode compact (3 control-plane nodes, 0 dedicated workers)
- **OCP version:** 4.20
- **Topology:** Per-student
- **Sizing:** 3 control plane (16 CPU, 64GB RAM) — may need more resources given the number of pre-installed operators
- **Automation approach:** Ansible
- **AI/MaaS:** MaaS (frontier model — GPT-4 via Azure OpenAI for OpenShift Lightspeed). Justification: Lightspeed module requires GPT-4 for natural language cluster management queries.
- **External services:** ldap.jumpcloud.com, Azure OpenAI, github.com, quay.io, registry.access.redhat.com
- **AAP version:** N/A — AAP not used
- **Non-GA products:** None (all products are GA)
