# Dev-Ops-10.5 CI/CD Platform

## Overview

### From Manual Builds to Automated Delivery

The CI/CD Platform is a companion project to the Kubernetes Platform Engineering & Operations Platform. The project focuses on source control integration, pipeline automation, continuous integration, build orchestration, and future Kubernetes-native delivery workflows using Jenkins and GitHub.

This platform provides a dedicated environment for validating Pipeline-as-Code practices, credential management, automated build triggers, agent architectures, and future containerized build execution.

## Portfolio Relationship

The CI/CD Platform complements the Kubernetes Platform Engineering & Operations Platform.

While Dev-Ops-10 focuses on Kubernetes infrastructure, storage, ingress, networking, observability, and platform operations, Dev-Ops-10.5 focuses on software delivery, continuous integration, pipeline management, and deployment automation.

Together the platforms support the following workflow:

GitHub  
→ Jenkins  
→ Kubernetes  
→ Application Delivery

Dev-Ops-10 provides the infrastructure foundation while Dev-Ops-10.5 provides the automation and delivery layer.

## Project Origin

This project originated from the need to build a dedicated CI/CD environment capable of integrating source control, automation workflows, and future Kubernetes deployment pipelines.

The platform was developed as a companion project to the Kubernetes Platform Engineering & Operations Platform to validate GitHub integration, Pipeline-as-Code, build automation, and future deployment workflows.

## Objectives

- Integrate Jenkins with GitHub.
- Develop and validate pipeline workflows.
- Implement Pipeline-as-Code.
- Implement automated build triggers.
- Implement agent-based build execution.
- Validate Kubernetes build agents.
- Establish CI/CD operational patterns for future platform integration.

## Environment

- GitHub
- Jenkins
- Kubernetes
- SMB CSI Storage
- NGINX Ingress
- HTTPS
- Git

## Technology Stack

### Source Control

- Git
- GitHub

### CI/CD Platform

- Jenkins LTS
- Declarative Pipelines
- Pipeline-as-Code

### Container Platform

- Kubernetes
- kubectl

### Storage

- SMB CSI Driver
- Persistent Volumes
- Persistent Volume Claims

### Networking

- NGINX Ingress
- HTTPS
- Internal DNS

### Security & Authentication

- Jenkins Credentials Store
- GitHub Fine-Grained Personal Access Tokens

## CI/CD Platform Components

### GitHub Repository

A dedicated GitHub repository hosts project documentation and Jenkins pipeline definitions. The repository serves as the source of truth for Pipeline-as-Code workflows.

### Jenkins Controller

Jenkins is deployed on Kubernetes using persistent SMB-backed storage and secured using HTTPS access.

### Pipeline-as-Code

Pipeline definitions are maintained in source control using Jenkinsfiles. Pipeline changes are version controlled, auditable, and automatically executed by Jenkins.

### Credentials Management

GitHub integration is implemented using Fine-Grained Personal Access Tokens securely stored within the Jenkins credential store.

### Poll SCM Automation

Automated build triggering is implemented using Jenkins Poll SCM.

Workflow:

Git Push  
→ GitHub  
→ Poll SCM  
→ Jenkins Pipeline  
→ Build Execution

This approach allows automated builds without exposing the Jenkins environment to the public Internet.

## Validation

### Validation Areas

#### Jenkins Platform Validation

- Jenkins deployment validated.
- Persistent SMB CSI storage validated.
- HTTPS access validated.
- Jenkins upgrade process validated.

#### GitHub Integration Validation

- Repository authentication validated.
- Jenkins credential management validated.
- Repository checkout validated.
- GitHub connectivity validated.

#### Pipeline Validation

- Pipeline-as-Code validated.
- Multi-stage pipeline execution validated.
- Shell execution validated.
- Environment validation demonstrated.
- Git repository validation demonstrated.

#### Automated Trigger Validation

- Poll SCM configured successfully.
- Automated source control polling validated.
- Automatic build execution validated.
- Builds successfully triggered by repository changes.

#### Outcome

The platform successfully demonstrated end-to-end CI/CD workflow capabilities including source control integration, automated build triggering, multi-stage pipeline execution, and Pipeline-as-Code practices.

## Screenshots

### Jenkins Deployment

### Jenkins HTTPS Access

### GitHub Integration

### Pipeline Success

### Poll SCM Validation

### Automated Build Trigger

## Lessons Learned

### Key Lessons

- Persistent storage design can directly impact CI/CD platform behavior.
- SMB-backed storage introduced OpenSSH temporary key permission challenges when using GitHub Deploy Keys.
- Fine-Grained GitHub Personal Access Tokens provided a reliable authentication alternative.
- Private infrastructure limits the usability of GitHub-hosted webhooks.
- Poll SCM provides an effective automated build trigger mechanism for private environments.
- Pipeline-as-Code simplifies change management and operational consistency.
- Separating platform engineering and CI/CD engineering improves maintainability and scalability.

## Key Outcomes

- Successfully deployed Jenkins on Kubernetes.
- Implemented SMB CSI-backed persistent storage.
- Configured HTTPS access.
- Integrated Jenkins with GitHub.
- Implemented secure credential management.
- Developed Pipeline-as-Code workflows.
- Built and executed multi-stage Jenkins pipelines.
- Validated automated repository polling.
- Validated automatic build triggering through repository changes.
- Established a CI/CD foundation for future Kubernetes deployment automation.

## Future Enhancements

- Dedicated Jenkins Agent Nodes
- Dynamic Kubernetes Agent Pods
- Container Image Build Automation
- Artifact Repository Integration
- Automated Testing Pipelines
- Deployment Pipelines
- GitOps Integration
- Jenkins Configuration as Code
- Kubernetes Deployment Automation

## Example Pipeline

```groovy
pipeline {
    agent any

    stages {

        stage('Checkout Validation') {
            steps {
                echo 'Repository checkout successful'
            }
        }

        stage('Environment Validation') {
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Git Validation') {
            steps {
                sh 'git rev-parse --short HEAD'
            }
        }

        stage('Build Validation') {
            steps {
                echo 'Simulated build completed successfully'
            }
        }
    }
}
```

## Status

### Completed

- Jenkins Deployment
- Persistent SMB Storage
- HTTPS Configuration
- GitHub Integration
- GitHub PAT Authentication
- Jenkins Credential Management
- Pipeline-as-Code
- Multi-Stage Pipeline Development
- Poll SCM Automation
- Automated Build Trigger Validation

### In Progress

- Jenkins Agent Architecture
- Build Worker Design

### Planned

- Dedicated Agent Nodes
- Kubernetes Agent Pods
- Container Image Build Automation
- Deployment Pipelines
- Advanced CI/CD Workflows
- Kubernetes Delivery Automation
