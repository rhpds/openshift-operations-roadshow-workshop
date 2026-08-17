# Module 04 — Ingress & Load Balancing

### Brief Overview

This module covers the OpenShift Ingress Controller (HAProxy-based) and advanced route configuration. Participants create routes with different TLS termination options, configure HTTP-to-HTTPS redirect, enable HSTS headers, and set up rate limiting. The module includes concurrent request testing to validate rate limiting behavior, giving participants hands-on experience with production-grade ingress configuration.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Network Administrators
- **Prerequisites:** Completion of Module 03 (application deployed and exposed via Route)
- **Duration:** 25 minutes

### Learning Objectives

- Configure routes with TLS termination options including edge, passthrough, and re-encrypt
- Implement HTTP-to-HTTPS redirect and HSTS headers on OpenShift routes
- Configure and verify rate limiting with concurrent request testing

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Explore the Ingress Controller configuration | 4 min |
| 2 | Create routes with different TLS termination modes | 6 min |
| 3 | Configure HTTP-to-HTTPS redirect | 4 min |
| 4 | Enable HSTS headers | 4 min |
| 5 | Configure rate limiting and test with concurrent requests | 7 min |

### Detailed Steps

1. Inspect the default IngressController with `oc get ingresscontroller -n openshift-ingress-operator`
2. Review the IngressController configuration details
3. Create a route with edge TLS termination using `oc create route edge`
4. Verify TLS termination is working with `curl`
5. Create a route with passthrough TLS termination
6. Configure HTTP-to-HTTPS redirect by patching the route with `oc patch route`
7. Verify redirect behavior with `curl -I`
8. Enable HSTS headers using `oc annotate route`
9. Verify HSTS header presence in response headers
10. Configure rate limiting annotations on a route
11. Run concurrent requests to test rate limiting behavior using `curl` in a loop
12. Observe rate limiting responses (HTTP 429) under load
13. Review Ingress Controller metrics in the monitoring dashboard

### Key Takeaways

- The OpenShift Ingress Controller (HAProxy) provides enterprise-grade routing out of the box
- TLS termination modes (edge, passthrough, re-encrypt) serve different security requirements
- HTTP-to-HTTPS redirect and HSTS headers enforce secure communication
- Rate limiting protects backend services from traffic spikes
- Route annotations provide fine-grained control over ingress behavior without modifying the Ingress Controller

### Infrastructure Notes

- Requires the default IngressController to be running and healthy
- DNS wildcard must be configured for the cluster domain
