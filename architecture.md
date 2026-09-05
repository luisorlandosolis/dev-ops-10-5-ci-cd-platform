# Architecture

## Overview

The CI/CD Platform provides build automation, source control integration, pipeline execution, and future Kubernetes-native build orchestration.

## High-Level Architecture

GitHub
→ Jenkins
→ Kubernetes
→ Application Delivery

## Core Components

### GitHub

- Source Control
- Pipeline Definitions
- Change Tracking

### Jenkins

- Pipeline Execution
- Credential Management
- Build Automation
- SCM Polling

### Kubernetes

- Jenkins Hosting
- Persistent Storage
- Future Dynamic Agents

## Storage Architecture

GitHub
→ Jenkins Controller
→ SMB CSI Persistent Volume
→ Jenkins Configuration

## Authentication Architecture

GitHub
→ Fine-Grained PAT
→ Jenkins Credential Store
→ Repository Access

## Build Workflow

Git Commit
→ Git Push
→ GitHub
→ Poll SCM
→ Jenkins Build
→ Pipeline Execution
