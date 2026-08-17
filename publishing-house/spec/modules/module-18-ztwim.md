# Module 18 — Zero-Trust Workload Identity Manager

### Brief Overview

This module covers the Zero Trust Workload Identity Manager (ZTWIM) based on the SPIFFE/SPIRE standard for workload identity. Participants configure SPIFFE-based certificate issuance, set up PostgreSQL with mTLS using SPIRE-issued certificates, enforce zero-trust communication between workloads, and observe automatic certificate rotation. The module demonstrates how cryptographic workload identity eliminates shared secrets and network-based trust assumptions.

### Audience and Time

- **Target personas:** Security Administrators, Platform Engineers, DevSecOps Engineers
- **Prerequisites:** Completion of Module 01 (cluster access); basic understanding of TLS, mTLS, and X.509 certificates
- **Duration:** 20 minutes

### Learning Objectives

- Configure SPIFFE/SPIRE-based workload identity and mTLS for PostgreSQL connections
- Verify zero-trust enforcement and automatic certificate rotation for workload communications

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Review the ZTWIM/SPIRE installation | 3 min |
| 2 | Configure SPIFFE-based certificates for PostgreSQL | 5 min |
| 3 | Enforce mTLS between workloads | 5 min |
| 4 | Verify zero-trust enforcement | 4 min |
| 5 | Observe automatic certificate rotation | 3 min |

### Detailed Steps

1. Verify the ZTWIM/SPIRE components are running in the cluster
2. Review the SPIRE server and agent configuration
3. Deploy a PostgreSQL instance configured to require mTLS
4. Configure SPIRE to issue certificates for the PostgreSQL workload
5. Examine the issued certificate with `openssl x509 -text`
6. Verify the SPIFFE ID in the certificate's SAN (Subject Alternative Name)
7. Connect to PostgreSQL using the SPIRE-issued certificate with `psql`
8. Verify the connection succeeds with valid mTLS credentials
9. Attempt a connection without a valid certificate and verify it is rejected
10. Deploy a client workload with SPIRE-issued identity
11. Verify the client can connect to PostgreSQL using mTLS with `oc run`
12. Monitor the certificate expiration time
13. Wait for automatic certificate rotation (or trigger it)
14. Verify the new certificate is issued and the connection continues without interruption
15. Discuss zero-trust principles and how SPIFFE/SPIRE eliminates network-based trust

### Key Takeaways

- SPIFFE/SPIRE provides cryptographic workload identity independent of network location
- mTLS enforces mutual authentication between communicating workloads
- Zero-trust eliminates the assumption that network boundaries provide security
- Automatic certificate rotation removes the operational burden of manual certificate management
- ZTWIM integrates with OpenShift to provide identity attestation based on pod metadata

### Infrastructure Notes

- ZTWIM/SPIRE operator must be pre-installed
- PostgreSQL must be deployable within the cluster
- Certificate rotation intervals should be short enough to observe during the lab
