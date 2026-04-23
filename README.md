# Self-Hosted Infrastructure & Automation Platform

Containerized service stack deployed on a Proxmox bare-metal host. Built for secure remote access, automated workflow orchestration, and reliable service delivery.

## 🏗 Architecture
- **Host**: Proxmox VE (bare metal)
- **Container Runtime**: Docker Compose with isolated networks
- **Remote Access**: Tailscale (zero-trust mesh, no public port exposure)
- **Automation**: Webhook-driven pipelines, scheduled maintenance, API integrations
- **Security**: Least-privilege configs, externalized secrets, read-only volumes where applicable

## 🚀 Deployment
All services are defined in `compose/docker-compose.yml` and driven by environment variables. Tailscale handles secure remote access without NAT or port forwarding.

```bash
# Start stack
docker compose -f compose/docker-compose.yml --env-file compose/.env up -d
