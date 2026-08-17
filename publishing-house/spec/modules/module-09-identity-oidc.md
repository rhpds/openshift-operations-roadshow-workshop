# Module 09 — Identity - OIDC

### Brief Overview

This module covers OIDC identity provider integration with OpenShift using Red Hat build of Keycloak (RHBK). Participants deploy a Keycloak instance, create a realm with users and groups, configure OpenShift to use Keycloak as an OIDC provider, set up automatic group sync from OIDC token claims, and implement RBAC based on Keycloak-managed groups. This provides a self-contained identity management solution without external dependencies.

### Audience and Time

- **Target personas:** Platform Engineers, Security Administrators, Identity and Access Management specialists
- **Prerequisites:** Completion of Module 01 (cluster-admin access); basic understanding of OIDC and RBAC concepts
- **Duration:** 20 minutes

### Learning Objectives

- Deploy Red Hat build of Keycloak and configure it as an OIDC identity provider for OpenShift
- Implement automatic group sync from OIDC token claims and configure group-based RBAC

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Deploy Red Hat build of Keycloak | 4 min |
| 2 | Create realm, users, and groups in Keycloak | 5 min |
| 3 | Configure OpenShift OIDC identity provider | 5 min |
| 4 | Set up group sync from token claims | 3 min |
| 5 | Configure RBAC and test access | 3 min |

### Detailed Steps

1. Apply the Keycloak CR to deploy an instance with `oc apply`
2. Wait for the Keycloak pod to reach Running state
3. Create a Route for the Keycloak admin console with `oc create route edge`
4. Access the Keycloak admin console and create a new realm
5. Create users in the realm with appropriate passwords
6. Create groups and assign users to groups
7. Configure a client in Keycloak for OpenShift OIDC integration
8. Add group membership as a token claim (groups mapper)
9. Configure the OAuth resource on OpenShift to add the OIDC identity provider
10. Wait for the authentication operator to reconcile
11. Test OIDC login with `oc login` using a Keycloak user
12. Verify group membership is synced from token claims
13. Assign RBAC roles to groups with `oc adm policy add-cluster-role-to-group`
14. Test that users inherit permissions through their Keycloak group membership

### Key Takeaways

- Red Hat build of Keycloak provides a self-hosted identity provider for OpenShift
- OIDC integration supports automatic group sync through token claims without scheduled sync jobs
- Groups mapper in Keycloak embeds group membership in the ID token
- OIDC and LDAP identity providers can coexist on the same OpenShift cluster
- Keycloak provides a web-based admin console for user and group management

### Infrastructure Notes

- Keycloak operator must be pre-installed
- Requires persistent storage for Keycloak state
- Route must be TLS-terminated for OIDC redirect URIs
