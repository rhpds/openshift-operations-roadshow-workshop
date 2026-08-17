# Module 06 — Debugging & Troubleshooting

### Brief Overview

This module presents six intentionally broken microservices, each exhibiting a different common failure mode. Participants diagnose and fix ImagePullBackOff, CrashLoopBackOff, resource constraint violations, CreateContainerConfigError, service selector mismatches, and SCC permission denied errors. The module teaches a systematic Observe-Diagnose-Fix-Verify workflow for troubleshooting pod failures on OpenShift.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Application Operators
- **Prerequisites:** Completion of Modules 01-03 (CLI familiarity, understanding of pods and deployments)
- **Duration:** 15 minutes

### Learning Objectives

- Troubleshoot six common pod failure modes using a systematic Observe-Diagnose-Fix-Verify workflow
- Analyze pod events, logs, and configuration to identify root causes of deployment failures

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Introduction to the broken microservices environment | 1 min |
| 2 | Fix 1: ImagePullBackOff | 2 min |
| 3 | Fix 2: CrashLoopBackOff | 2 min |
| 4 | Fix 3: Resource constraint violation | 2 min |
| 5 | Fix 4: CreateContainerConfigError | 3 min |
| 6 | Fix 5: Service selector mismatch | 2 min |
| 7 | Fix 6: SCC permission denied | 3 min |

### Detailed Steps

1. Navigate to the project containing the six broken microservices
2. List all pods and observe their statuses with `oc get pods`
3. **ImagePullBackOff:** Describe the pod to identify the incorrect image reference, fix it with `oc set image`
4. Verify the pod transitions to Running
5. **CrashLoopBackOff:** Check pod logs with `oc logs` to identify the application error, apply the fix
6. Verify the pod stabilizes and stops restarting
7. **Resource constraint violation:** Describe the pod to identify resource limit issues, adjust resource requests/limits
8. Verify the pod is scheduled and running
9. **CreateContainerConfigError:** Describe the pod to find the missing ConfigMap reference, create the missing ConfigMap with `oc create configmap`
10. Verify the pod starts successfully
11. **Service selector mismatch:** Compare the Service selector labels with pod labels, patch the deployment to align labels
12. Verify the Service endpoints are populated and traffic flows
13. **SCC permission denied:** Check pod events for SCC violations, patch the deployment with appropriate security context or ServiceAccount
14. Verify the pod runs with the correct SCC

### Key Takeaways

- A systematic Observe-Diagnose-Fix-Verify workflow accelerates troubleshooting
- `oc describe pod` and `oc logs` are the two most important diagnostic commands
- ImagePullBackOff and CrashLoopBackOff are the most common pod failure modes
- SCCs are an OpenShift-specific security mechanism that can block workloads expecting root or elevated privileges
- Service selector mismatches are a frequent cause of "application unreachable" issues

### Infrastructure Notes

- Six intentionally broken microservices must be pre-deployed in the lab environment
- Broken applications should cover the six failure modes described above
