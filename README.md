# CI/CD Pipeline Final Project

## Project Overview
This repository contains the CI/CD pipeline configuration and implementation for the final project. It utilizes **GitHub Actions** for continuous integration (CI) and **Tekton** on Red Hat OpenShift for continuous delivery (CD) pipeline orchestrations.

## Objectives
- Automatically lint the codebase utilizing `flake8`.
- Execute automated Python unit testing utilizing `nose`.
- Clean up old workspace environments securely.
- Deploy the application container via Tekton pipelines on OpenShift Cluster.

## Repository Structure
- `.github/workflows/workflow.yml`: Contains the GitHub Actions configuration.
- `.tekton/tasks.yml`: Contains the Tekton cluster task definitions.
- `/service/`: The Python Flask microservice backend endpoints.

## Automations Workflow
1. A developer pushes code or opens a pull request towards the `main` branch.
2. GitHub Actions are triggered automatically to execute syntax linting and coverage tests.
3. Upon success, changes interact with the remote OpenShift cluster utilizing Tekton pipelines.
4. Active `pipelinerun` builds the container images and deploys them gracefully strictly using a pre-defined PersistentVolumeClaim (PVC).
