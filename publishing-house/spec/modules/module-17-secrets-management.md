# Module 17 — Secrets Management

### Brief Overview

This module covers external secrets management on OpenShift using HashiCorp Vault and the External Secrets Operator (ESO). Participants deploy Vault via Helm, configure Kubernetes authentication, inject secrets into pods using the Vault Agent Injector pattern, and then implement the External Secrets Operator pattern for declarative secret synchronization. The module demonstrates two complementary approaches to managing secrets outside of Kubernetes native Secret objects.

### Audience and Time

- **Target personas:** Platform Engineers, Security Administrators, DevSecOps Engineers
- **Prerequisites:** Completion of Module 01 (cluster access); basic understanding of Kubernetes Secrets and Helm
- **Duration:** 25 minutes

### Learning Objectives

- Deploy HashiCorp Vault on OpenShift and configure Kubernetes authentication with the Vault Agent Injector pattern
- Implement the External Secrets Operator pattern for declarative secret synchronization from Vault

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Deploy HashiCorp Vault via Helm | 5 min |
| 2 | Configure Kubernetes authentication in Vault | 5 min |
| 3 | Vault Agent Injector pattern | 7 min |
| 4 | External Secrets Operator pattern | 8 min |

### Detailed Steps

1. Add the HashiCorp Helm repository
2. Install Vault using `helm install` with OpenShift-compatible values
3. Wait for the Vault pod to reach Running state
4. Initialize and unseal Vault
5. Enable the Kubernetes auth method using `vault auth enable kubernetes`
6. Configure the Kubernetes auth backend with the cluster's service account token
7. Create a Vault policy and role for the application
8. Write a test secret to Vault using `vault kv put`
9. Deploy an application with Vault Agent Injector annotations
10. Verify the secret is injected into the pod's filesystem
11. Install the External Secrets Operator
12. Create a SecretStore resource pointing to Vault with `oc apply`
13. Create an ExternalSecret resource that references a Vault path with `oc apply`
14. Verify a Kubernetes Secret is automatically created and synced from Vault
15. Update the secret in Vault and verify the ExternalSecret syncs the change
16. Compare the two patterns: Vault Agent Injector vs. External Secrets Operator

### Key Takeaways

- External secrets management separates secret lifecycle from application deployment
- Vault Agent Injector injects secrets as files into pod containers at runtime
- External Secrets Operator creates native Kubernetes Secrets synchronized from external stores
- Kubernetes auth in Vault uses ServiceAccount tokens for zero-credential authentication
- Both patterns avoid storing sensitive data in Git or Kubernetes Secret manifests
- ESO provides a more Kubernetes-native experience; Vault Agent provides runtime injection

### Infrastructure Notes

- Helm must be available in the lab environment
- Vault Helm chart must be accessible from the cluster
- External Secrets Operator must be pre-installed or installable from OperatorHub
