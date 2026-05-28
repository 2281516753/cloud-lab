# Cloud Lab ☁️ 云基础设施实验平台

[![Docker](https://img.shields.io/badge/Docker-✓-2496ED?logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen)]()

> 基于 Docker Compose 的云基础设施实验环境，用于学习和验证云计算核心技术。
> Docker Compose-based cloud infrastructure lab for learning and practicing core cloud technologies.

## 实验环境 / Lab Modules

| 实验 Lab | 内容 Content | 目录 |
|-----------|-------------|------|
| 01-Nginx-LB | Nginx 负载均衡 + 多后端 / Load balancing + multi-backend | `lab01-nginx-lb/` |
| 02-MySQL-Cluster | MySQL 主从复制 + 读写分离 / Master-slave replication | `lab02-mysql-cluster/` |
| 03-Redis-HA | Redis Sentinel 高可用 / High availability | `lab03-redis-ha/` |
| 04-Monitoring | Prometheus + Grafana 监控栈 / Monitoring stack | `lab04-monitoring/` |
| 05-Network | 自定义 Docker 网络 + 多子网互联 / Custom networks | `lab05-network/` |

## 快速开始 / Quick Start

```bash
git clone https://github.com/2281516753/cloud-lab.git
cd cloud-lab

# 启动某个实验 / Start a lab
cd lab01-nginx-lb
docker compose up -d

# 查看运行状态 / Check status
docker compose ps
```

## 环境要求 / Requirements

- Docker 20.10+
- Docker Compose v2+
- 至少 4GB 可用内存 / 4GB+ RAM recommended

## 学习路线 / Learning Path

1. **负载均衡与反向代理** — 理解 L4/L7 负载均衡原理 / Understand L4/L7 load balancing
2. **数据库高可用** — 掌握主从复制、读写分离架构 / Master-slave replication & read/write splitting
3. **缓存集群** — 学习 Redis Sentinel 故障转移机制 / Redis Sentinel failover
4. **可观测性** — 搭建企业级监控体系 / Build enterprise monitoring
5. **网络架构** — 实践容器网络、跨子网通信 / Container networking & cross-subnet

## CI/CD

本项目采用 Docker Compose 进行自动化测试验证。每个实验目录下的 `docker compose up -d` 可作为 CI 流水线中的集成测试步骤，验证各服务的容器启动、健康检查和基本连通性。

Each lab module supports CI integration: `docker compose up -d` → `docker compose ps` (health check) → `docker compose down` (cleanup).

## 使用场景 / Use Cases

### 场景一：面试前快速搭建负载均衡实验环境

面试中常被问到 Nginx 反向代理、负载均衡算法、健康检查等。进入 `lab01-nginx-lb/` 执行 `docker compose up -d`，即可获得完整实验环境。

### 场景二：教学演示中一键拉起监控栈

进入 `lab04-monitoring/`，一条命令启动 Prometheus + Grafana，直接展示指标采集与可视化全流程。

### 场景三：零成本学习 MySQL 高可用

通过 `lab02-mysql-cluster/` 在本地 Docker 环境模拟主库写入、从库同步、故障切换。

### 场景四：验证容器网络原理

`lab05-network/` 自动创建多子网拓扑，可通过 `docker exec` 实际测试跨子网连通性。

---

### Quick Use Cases (EN)

- **Interview prep**: One command to spin up Nginx load balancing lab
- **Teaching**: Instant Prometheus + Grafana stack for demos
- **MySQL HA**: Master-slave cluster simulation with zero cloud cost
- **Networking**: Multi-subnet topology for hands-on container networking

## Author

Wang Jiong (王炯) — Network Engineering student, cloud computing enthusiast.

## License

MIT
