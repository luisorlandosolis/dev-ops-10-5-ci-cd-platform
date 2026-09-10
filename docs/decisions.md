# Architectural Decisions

## ADR-001: Jenkins Hosted on Kubernetes

### Status

Accepted

### Decision

Deploy Jenkins as a workload on the Kubernetes Platform Engineering & Operations Platform.

### Rationale

The Kubernetes platform already provided:

- Container orchestration
- Persistent storage services
- Ingress capabilities
- Platform scalability
- Future cloud-native integration

### Outcome

Jenkins was successfully deployed and operated as a Kubernetes-hosted platform service and became the foundation of the CI/CD Platform.

---

## ADR-002: SMB CSI Persistent Storage

### Status

Accepted

### Decision

Use SMB CSI-backed Persistent Volumes and Persistent Volume Claims for Jenkins persistent storage.

### Rationale

Requirements included:

- Jenkins configuration retention
- Build history retention
- Credential persistence
- Plugin persistence
- Recovery after pod recreation

### Outcome

Jenkins configuration, plugins, credentials, and build history persist across upgrades, pod recreation, and maintenance activities.

---

## ADR-003: HTTPS Access Through NGINX Ingress

### Status

Accepted

### Decision

Publish Jenkins through HTTPS using NGINX Ingress.

### Rationale

Requirements included:

- Encrypted administrative access
- Secure browser connectivity
- Consistent platform ingress architecture
- Centralized application publishing

### Outcome

The Jenkins platform was successfully published via HTTPS and integrated into the Kubernetes ingress architecture.

---

## ADR-004: GitHub as Source Control Platform

### Status

Accepted

### Decision

Use GitHub as the authoritative source control platform.

### Rationale

GitHub provides:

- Source control
- Repository management
- Documentation management
- Jenkins integration
- Pipeline-as-Code support

### Outcome

GitHub became the system of record for documentation, Jenkinsfiles, automation workflows, and future software delivery pipelines.

---

## ADR-005: Pipeline-as-Code

### Status

Accepted

### Decision

Store all pipeline definitions in source control using Jenkinsfiles.

### Rationale

Benefits include:

- Version control
- Change tracking
- Auditing
- Portability
- Repeatability

### Outcome

Pipeline logic is maintained within GitHub repositories and executed automatically by Jenkins.

---

## ADR-006: GitHub PAT Authentication

### Status

Accepted

### Decision

Use Fine-Grained Personal Access Tokens for GitHub authentication.

### Rationale

Requirements included:

- Secure repository access
- Reliable authentication
- Compatibility with Jenkins automation
- Reduced administrative overhead

### Outcome

GitHub integration was successfully validated and became the operational authentication model for source-control connectivity.

---

## ADR-007: Poll SCM Automation

### Status

Accepted

### Decision

Use Poll SCM for automated repository change detection.

### Rationale

The CI/CD platform operates on private internal infrastructure and is not directly exposed to the public Internet.

Poll SCM provides:

- Automated build triggering
- Repository monitoring
- Internal-only operation
- Simplified integration

### Outcome

Automated build execution was successfully validated through repository polling.

---

## ADR-008: Static Agent Architecture

### Status

Accepted

### Decision

Implement a dedicated static Jenkins agent for infrastructure-focused automation workloads.

### Rationale

Static agents provide:

- Predictable execution environments
- Persistent toolsets
- Infrastructure automation support
- Operational validation support

### Outcome

Static agent execution was successfully validated and became the preferred model for infrastructure and operational workloads.

---

## ADR-009: Dynamic Kubernetes Agent Architecture

### Status

Accepted

### Decision

Implement dynamic Kubernetes agents using Jenkins Kubernetes Cloud integration.

### Rationale

Dynamic agents provide:

- Disposable execution environments
- Automated provisioning
- Kubernetes-native execution
- Scalable build capacity

### Outcome

Dynamic Kubernetes agents were successfully provisioned, executed workloads, and automatically removed upon job completion.

---

## ADR-010: ServiceAccount and RBAC Security Model

### Status

Accepted

### Decision

Use Kubernetes ServiceAccounts and RBAC authorization for Jenkins Kubernetes Cloud integration.

### Rationale

Requirements included:

- Controlled API access
- Least-privilege authorization
- Secure agent provisioning
- Kubernetes-native authentication

### Outcome

Jenkins successfully authenticated to Kubernetes and provisioned dynamic build agents using ServiceAccount-backed authorization.

---

## ADR-011: Operational Workload Validation

### Status

Accepted

### Decision

Validate the CI/CD platform using operational workloads rather than synthetic demonstration pipelines.

### Rationale

Operational workloads provide validation for:

- Automation workflows
- Application availability
- Service health
- Infrastructure connectivity
- Platform operations

### Outcome

The Weather Platform was selected as the primary validation workload for CI/CD platform verification.

---

## ADR-012: Hybrid Infrastructure Validation

### Status

Accepted

### Decision

Extend validation beyond local infrastructure to include hybrid cloud resources.

### Rationale

Requirements included:

- Disaster recovery validation
- Multi-site service validation
- Connectivity verification
- Real-world operational testing

### Outcome

The platform successfully validated local application services, WireGuard connectivity, NGINX load balancing, and Azure-hosted disaster recovery resources through Jenkins automation.

---

## ADR-013: Dual Execution Model

### Status

Accepted

### Decision

Support both static and dynamic execution models within the CI/CD platform.

### Rationale

Different workloads have different execution requirements.

Static agents are optimized for:

- Infrastructure automation
- Operational validation
- Administrative tasks

Dynamic agents are optimized for:

- Cloud-native workloads
- Disposable execution
- Elastic build capacity

### Outcome

The platform successfully validated both execution models and established a foundation for future software delivery automation.

---

## Summary

The CI/CD platform was designed around the following core architectural principles:

- Kubernetes-hosted Jenkins operations
- Persistent storage through SMB CSI
- GitHub-driven Pipeline-as-Code workflows
- Secure credential management
- Static and dynamic execution models
- Operational workload validation
- Hybrid infrastructure validation
- Future software delivery integration
- Future GitOps and ArgoCD integration
