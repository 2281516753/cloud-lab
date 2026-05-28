# Cloud Lab ☁️

[![Docker](https://img.shields.io/badge/Docker-✓-2496ED?logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen)]()

> [📖 中文版 / Chinese Version](README_CN.md)

Docker Compose-based cloud infrastructure lab for learning core cloud technologies — Nginx load balancing, Prometheus/Grafana monitoring, Redis/MySQL high availability.

## Lab Modules

| Lab | Content | Directory |
|-----|---------|-----------|
| 01-Nginx-LB | Nginx load balancing + multi-backend | `lab01-nginx-lb/` |
| 02-MySQL-Cluster | MySQL master-slave replication + read/write splitting | `lab02-mysql-cluster/` |
| 03-Redis-HA | Redis Sentinel high availability | `lab03-redis-ha/` |
| 04-Monitoring | Prometheus + Grafana monitoring stack | `lab04-monitoring/` |
| 05-Network | Custom Docker networks + cross-subnet | `lab05-network/` |

## Quick Start

```bash
git clone https://github.com/2281516753/cloud-lab.git
cd cloud-lab
cd lab01-nginx-lb
docker compose up -d
docker compose ps
```

## Requirements

- Docker 20.10+
- Docker Compose v2+
- 4GB+ RAM recommended

## Learning Path

1. **Load Balancing** — Understand L4/L7 load balancing with Nginx
2. **Database HA** — Master-slave replication & read/write splitting
3. **Cache Clusters** — Redis Sentinel failover mechanisms
4. **Observability** — Enterprise monitoring with Prometheus + Grafana
5. **Networking** — Container networking & cross-subnet communication

## CI/CD

Each lab supports CI integration: `docker compose up -d` → `docker compose ps` (health check) → `docker compose down` (cleanup).

## Use Cases

- **Interview prep**: One command to spin up Nginx load balancing lab
- **Teaching**: Instant Prometheus + Grafana stack for live demos
- **MySQL HA**: Master-slave cluster simulation with zero cloud cost
- **Networking**: Multi-subnet topology for hands-on container networking

## Author

Wang Jiong (王炯) — Network Engineering student, cloud computing enthusiast.

## License

MIT