# Homelab Deployment Workflows

This repository contains GitHub Actions workflows used to deploy and maintain services running in my homelab.

The workflows connect securely to my server over Tailscale and perform routine deployment tasks such as pulling the latest container images and restarting Docker Compose services.

## Features

* GitHub Actions automation
* Manual deployments using `workflow_dispatch`
* Service selection via dropdown inputs
* Secure connectivity using Tailscale
* SSH public key authentication
* Docker Compose deployments
* Automatic cleanup of unused Docker images

## Deployment Flow

```text
GitHub Actions
        │
        ▼
Join Tailscale Tailnet
        │
        ▼
SSH into Ubuntu Server
        │
        ▼
docker compose pull
        │
        ▼
docker compose up -d
        │
        ▼
docker image prune -af
```

## Supported Services

* Bazarr
* Cross-seed
* FlareSolverr
* go2rtc
* Grafana
* Home Assistant
* Jellyfin
* Nginx
* Node Exporter
* Prometheus
* Prowlarr
* Radarr
* Seerr
* Smartctl Exporter
* Sonarr
* Transmission
* WordPress

## Security

No secrets are stored in this repository.

Authentication is handled using:

* GitHub Actions Secrets
* Tailscale OAuth
* SSH public key authentication

## Purpose

This repository exists to centralize deployment automation for my homelab and to serve as a practical learning project for CI/CD, Linux automation, and infrastructure operations.
