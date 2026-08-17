# Module 14 — Lightspeed

### Brief Overview

This module covers OpenShift Lightspeed (OLS), the AI assistant for OpenShift operations. Participants deploy OpenShift Lightspeed, connect it to Azure OpenAI GPT-4, and use it for learning OpenShift concepts, generating YAML manifests from natural language, and troubleshooting cluster issues. The module demonstrates how AI-assisted operations can accelerate common administrative tasks.

### Audience and Time

- **Target personas:** Platform Engineers, SREs, Cluster Administrators
- **Prerequisites:** Completion of Module 01 (cluster access)
- **Duration:** 20 minutes

### Learning Objectives

- Deploy OpenShift Lightspeed and configure it with an Azure OpenAI GPT-4 backend
- Explore AI-assisted cluster management for concept learning, YAML generation, and troubleshooting

### Lab Structure

| Section | Title | Duration |
|---------|-------|----------|
| 1 | Deploy OpenShift Lightspeed | 5 min |
| 2 | Configure the Azure OpenAI connection | 4 min |
| 3 | Use Lightspeed for concept learning | 3 min |
| 4 | Generate YAML from natural language | 4 min |
| 5 | Troubleshoot with Lightspeed | 4 min |

### Detailed Steps

1. Apply the OLSConfig CR to deploy OpenShift Lightspeed with `oc apply`
2. Verify the Lightspeed deployment is running with `oc get olsconfig`
3. Configure the Azure OpenAI API endpoint and credentials
4. Verify connectivity to the Azure OpenAI backend
5. Access the Lightspeed interface in the OpenShift web console
6. Ask Lightspeed to explain an OpenShift concept (e.g., "What is a MachineSet?")
7. Evaluate the response for accuracy and completeness
8. Ask Lightspeed to generate YAML for a specific resource (e.g., "Create a NetworkPolicy that allows traffic only from namespace X")
9. Review the generated YAML for correctness
10. Apply the generated YAML and verify the resource is created
11. Present a troubleshooting scenario to Lightspeed (e.g., "Why is my pod in CrashLoopBackOff?")
12. Follow Lightspeed's troubleshooting suggestions
13. Discuss the capabilities and limitations of AI-assisted operations

### Key Takeaways

- OpenShift Lightspeed provides context-aware AI assistance directly in the web console
- AI can accelerate common tasks like YAML generation and concept explanation
- Lightspeed uses MaaS (Model as a Service) via Azure OpenAI without requiring local GPU resources
- AI-generated output should always be reviewed before applying to production clusters
- Lightspeed complements, rather than replaces, operational expertise

### Infrastructure Notes

- OpenShift Lightspeed operator must be pre-installed
- Requires Azure OpenAI API credentials with access to GPT-4
- No GPU required (MaaS pattern — inference runs on Azure)
