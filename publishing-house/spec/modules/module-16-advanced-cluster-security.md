# Module 16 — Advanced Cluster Security

### Brief Overview

This module covers Red Hat Advanced Cluster Security (RHACS) for securing containerized workloads on OpenShift. Participants deploy intentionally insecure applications, run compliance scans against industry standards (CIS, PCI-DSS, STIG), implement Policy-as-Code to block runtime anomalies, and detect and audit policy violations. The module demonstrates a security-first approach to container platform operations.

### Audience and Time

- **Target personas:** Security Administrators, Platform Engineers, Compliance Engineers
- **Prerequisites:** Completion of Module 01 (cluster access); basic container security concepts
- **Duration:** 20 minutes

### Learning Objectives

- Implement compliance scanning against CIS, PCI-DSS, and STIG benchmarks using RHACS
- Configure Policy-as-Code rules to detect and block runtime security violations

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Deploy intentionally insecure applications | 3 min |
| 2 | Run compliance scans (CIS, PCI-DSS, STIG) | 5 min |
| 3 | Review compliance results and violations | 4 min |
| 4 | Configure Policy-as-Code for runtime enforcement | 5 min |
| 5 | Detect and audit violations | 3 min |

### Detailed Steps

1. Deploy intentionally insecure application manifests with `oc apply`
2. Access the RHACS console (Central)
3. Navigate to the compliance dashboard
4. Run a CIS benchmark compliance scan
5. Run PCI-DSS and STIG compliance scans
6. Review the compliance results and identify failing controls
7. Examine specific violations and their remediation guidance
8. Navigate to the policy management section
9. Create a new security policy to block a specific runtime anomaly (e.g., exec into container)
10. Apply the SecurityPolicy with enforcement enabled with `oc apply`
11. Trigger the policy violation by performing the blocked action
12. Verify the violation is detected and blocked by RHACS
13. Review the violation event in the RHACS audit log
14. Discuss defense-in-depth strategies combining RHACS with NetworkPolicies and SCCs

### Key Takeaways

- RHACS provides continuous compliance scanning against industry benchmarks
- Policy-as-Code enables declarative security enforcement at runtime
- Compliance scans identify gaps between current configuration and regulatory requirements
- Runtime policies can detect and block suspicious behavior (process execution, network activity)
- RHACS complements OpenShift SCCs and NetworkPolicies for defense-in-depth security

### Infrastructure Notes

- RHACS (Central and SecuredCluster) must be pre-installed
- Compliance Operator must be installed for benchmark profiles
- Intentionally insecure test applications must be available
