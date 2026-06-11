# Cloud Lab ☁️

[![Docker](https://img.shields.io/badge/Docker-✓-2496ED?logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen)]()

> [📖 中文版 / Chinese Version](README_CN.md)

Docker Compose-based cloud infrastructure lab for learning core cloud technologies — Nginx load balancing, MySQL HA, Redis Sentinel, Prometheus/Grafana monitoring, and container networking.

## Lab Modules

| Lab | Content | Directory | Status |
|-----|---------|-----------|--------|
| 01-Nginx-LB | Nginx load balancing + multi-backend | `lab01-nginx-lb/` | ✅ Done |
| 02-MySQL-Cluster | MySQL master-slave replication + ProxySQL read/write splitting | `lab02-mysql-cluster/` | ✅ Done |
| 03-Redis-HA | Redis Sentinel high availability (1M+2R+3S) | `lab03-redis-ha/` | ✅ Done |
| 04-Monitoring | Prometheus + Grafana monitoring stack | `lab04-monitoring/` | ✅ Done |
| 05-Network | Custom Docker networks + multi-subnet | `lab05-network/` | ✅ Done |
| 06-PostgreSQL | PostgreSQL streaming replication + pgAdmin | `lab06-postgresql/` | ✅ Done |

## Quick Start

```bash
git clone https://github.com/2281516753/cloud-lab.git
cd cloud-lab

# Spin up any lab
cd lab01-nginx-lb && docker compose up -d && docker compose ps
cd lab02-mysql-cluster && docker compose up -d && docker compose ps
cd lab03-redis-ha && docker compose up -d && docker compose ps
```

## Requirements

- Docker 20.10+
- Docker Compose v2+
- 4GB+ RAM recommended

## Learning Path

1. **Load Balancing** — Understand L4/L7 load balancing with Nginx
2. **Database HA** — MySQL master-slave replication & read/write splitting
3. **Cache Clusters** — Redis Sentinel failover mechanisms
4. **Observability** — Enterprise monitoring with Prometheus + Grafana
5. **Networking** — Container networking & multi-subnet communication

## Use Cases

- **Interview prep**: One command to spin up Nginx load balancing lab
- **Teaching**: Instant Prometheus + Grafana stack for live demos
- **MySQL HA**: Master-slave cluster simulation with zero cloud cost
- **Networking**: Multi-subnet topology for hands-on container networking

## Related Projects

| Project | Description |
|---------|-------------|
| [net-auto](https://github.com/2281516753/net-auto) | Network automation toolkit |
| [wsl-dev-setup](https://github.com/2281516753/wsl-dev-setup) | WSL2 dev environment one-click setup |
| [net-diag-html](https://github.com/2281516753/net-diag-html) | Browser-based network diagnostics |
| [net-diag-demo](https://github.com/2281516753/net-diag-demo) | Full-stack network diagnostics dashboard |

## Author

**Wang Jiong (王炯)** — Network Engineering student, cloud computing career path.

[![GitHub](https://img.shields.io/badge/GitHub-2281516753-181717?logo=github)](https://github.com/2281516753)

## License

MIT