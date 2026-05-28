# Cloud Lab ☁️ 云基础设施实验平台

[![Docker](https://img.shields.io/badge/Docker-✓-2496ED?logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen)]()

> [📖 English Version / 英文版](README.md)

基于 Docker Compose 的云基础设施实验环境，用于学习和验证云计算核心技术 —— Nginx 负载均衡、Prometheus/Grafana 监控、Redis/MySQL 高可用。

## 实验模块

| 实验 | 内容 | 目录 |
|------|------|------|
| 01-Nginx-LB | Nginx 负载均衡 + 多后端 | `lab01-nginx-lb/` |
| 02-MySQL-Cluster | MySQL 主从复制 + 读写分离 | `lab02-mysql-cluster/` |
| 03-Redis-HA | Redis Sentinel 高可用 | `lab03-redis-ha/` |
| 04-Monitoring | Prometheus + Grafana 监控栈 | `lab04-monitoring/` |
| 05-Network | 自定义 Docker 网络 + 多子网互联 | `lab05-network/` |

## 快速开始

```bash
git clone https://github.com/2281516753/cloud-lab.git
cd cloud-lab
cd lab01-nginx-lb
docker compose up -d
docker compose ps
```

## 环境要求

- Docker 20.10+
- Docker Compose v2+
- 至少 4GB 可用内存

## 学习路线

1. **负载均衡** — 理解 L4/L7 负载均衡原理
2. **数据库高可用** — 掌握主从复制、读写分离架构
3. **缓存集群** — 学习 Redis Sentinel 故障转移
4. **可观测性** — 搭建企业级监控体系
5. **网络架构** — 实践容器网络、跨子网通信

## CI/CD

每个实验模块支持 CI 集成：`docker compose up -d` → `docker compose ps`（健康检查）→ `docker compose down`（清理）。

## 使用场景

- **面试准备**：一键搭建 Nginx 负载均衡实验环境
- **教学演示**：一条命令启动 Prometheus + Grafana 监控栈
- **MySQL 高可用**：零成本在本地 Docker 模拟主从集群
- **容器网络**：多子网拓扑，动手实践容器网络原理

## 作者

王炯 (Wang Jiong) — 网络工程专业，云计算爱好者。

## License

MIT