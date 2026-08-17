# Module 08 — Identity - LDAP

### Brief Overview

This module covers LDAP identity provider integration with OpenShift using JumpCloud as the directory service. Participants configure the LDAP identity provider, perform group sync to import LDAP groups into OpenShift, and implement group-based RBAC across development, testing, and production projects. The module concludes with testing permissions by logging in as different users and verifying access controls.

### Audience and Time

- **Target personas:** Platform Engineers, Security Administrators, Identity and Access Management specialists
- **Prerequisites:** Completion of Module 01 (cluster-admin access); basic understanding of LDAP and RBAC concepts
- **Duration:** 20 minutes

### Learning Objectives

- Integrate an LDAP identity provider with OpenShift using secure LDAP (LDAPS)
- Configure group sync and implement group-based RBAC across multiple projects

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Create LDAP bind credentials secret | 3 min |
| 2 | Configure the LDAP identity provider | 5 min |
| 3 | Sync LDAP groups to OpenShift | 4 min |
| 4 | Configure group-based RBAC for dev/test/prod | 5 min |
| 5 | Test permissions as different users | 3 min |

### Detailed Steps

1. Create a secret containing the LDAP bind password with `oc create secret`
2. Configure the OAuth resource to add the LDAP identity provider
3. Wait for the authentication operator to reconcile the new configuration
4. Test LDAP login with `oc login` using an LDAP user's credentials
5. Create an LDAP group sync configuration file
6. Run `oc adm groups sync` to import LDAP groups into OpenShift
7. Verify the synced groups with `oc get groups`
8. Create dev, test, and prod projects with `oc adm new-project`
9. Assign roles to groups using `oc adm policy add-cluster-role-to-group`
10. Grant the dev group edit access to the dev project
11. Grant the ops group admin access to all projects
12. Log in as a dev user with `oc login` and verify access to the dev project
13. Verify the dev user cannot access the prod project
14. Log in as an ops user and verify access to all projects

### Key Takeaways

- OpenShift supports multiple identity providers simultaneously via the OAuth configuration
- LDAP group sync imports directory groups as OpenShift groups for RBAC binding
- Group-based RBAC is more maintainable than individual user role assignments
- LDAPS (port 636) should always be used for production LDAP integration
- Group sync can be scheduled as a CronJob for continuous synchronization

### Infrastructure Notes

- Requires external LDAP service (JumpCloud at ldaps://ldap.jumpcloud.com:636)
- LDAP bind credentials must be pre-provisioned
- Test user accounts must exist in the LDAP directory
