<h1 align="center">EMCP Baseline NestJS Backend</h1>

<p align="center">
  A production‑ready NestJS backend service with Docker, Docker Compose, Helm chart support, and GitHub Actions CI/CD.
</p>

## Description

This project is a baseline NestJS backend service designed for cloud‑native environments. It provides a solid starting point that includes:
- A modular, TypeScript‑based NestJS server
- Docker and Docker Compose configuration for local development
- Helm charts for Kubernetes deployment
- GitHub Actions workflows for continuous integration and deployment

## Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [Docker](https://www.docker.com/)
- [Helm](https://helm.sh/)
- A Kubernetes cluster (for production deployments)

## Project Setup

Clone the repository and install dependencies:

```shell
# Clone the repository (if using the GitHub template, click "Use this template" from the repo page)
git clone https://github.com/enclaive/skele-type.git
cd skele-type/server
npm install
# Running the application
# Development mode with auto-reload
npm run start:dev
# Production mode
npm run start
# Lint and autofix with ESLint
npm run lint
# Format code with Prettier
npm run format
```

## Replacing Placeholders

This template uses placeholders (e.g., `{{service-name}}` and `{{namespace}}`) in various configuration files (such as Kubernetes manifests and Helm charts). To customize the template for your project:

* **Search for `{{service-name}}`:**
    Replace every instance of `{{service-name}}` with the actual name of your service (for example, `orders-api`, `backend`, etc.).
* **Search for `{{namespace}}`:**
    Replace `{{namespace}}` with the target Kubernetes namespace (for example, `emcp-staging`, `emcp-prod`, etc.).
* **Helm Integration:**
    If using Helm, these placeholders can be replaced dynamically via the `values.yaml` file. For example, use `{{ .Values.serviceName }}` in your templates and define `serviceName` in your Helm values file.

## GitHub Template Repository

This repository is designed to be used as a GitHub template:

1.  **Using the Template:**
    On GitHub, click the “Use this template” button on the repository’s main page. This will create a new repository with the same structure.
2.  **Customization:**
    After creating your new repository, update configuration files and replace all placeholders with values specific to your project.
3.  **Benefits:**
    This approach provides a consistent starting point across multiple projects and simplifies setup by pre-configuring CI/CD, Docker, and Helm deployments.

## Deployment

### Docker and Docker Compose

This repository includes a `Dockerfile` in the `docker/server` directory and a `docker-compose.yml` file at the root.

* **Dockerfile:**
    Located in `docker/server/Dockerfile`, it builds the NestJS service image.
* **Docker Compose:**
    Use the following command to build and run the service along with its dependencies:
```shell
docker-compose up --build
```
