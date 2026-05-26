# Cloud Lab

[![Docker](https://img.shields.io/badge/Docker-✓-2496ED?logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

基于 Docker Compose 的云基础设施实验环境，用于学习和验证云计算核心技术。

## 实验环境

| 实验 | 内容 | 目录 |
|------|------|------|
| 01-Nginx-LB | Nginx 负载均衡 + 多后端 | `lab01-nginx-lb/` |
| 02-MySQL-Cluster | MySQL 主从复制 + 读写分离 | `lab02-mysql-cluster/` |
| 03-Redis-HA | Redis Sentinel 高可用 | `lab03-redis-ha/` |
| 04-Monitoring | Prometheus + Grafana 监控栈 | `lab04-monitoring/` |
| 05-Network | 自定义 Docker 网络 + 多子网互联 | `lab05-network/` |

## 快速开始

```bash
# 克隆仓库
git clone https://github.com/2281516753/cloud-lab.git
cd cloud-lab

# 启动某个实验
cd lab01-nginx-lb
docker compose up -d

# 查看运行状态
docker compose ps
```

## 环境要求

- Docker 20.10+
- Docker Compose v2+
- 至少 4GB 可用内存

## 学习路线

1. **负载均衡与反向代理** — 理解 L4/L7 负载均衡原理
2. **数据库高可用** — 掌握主从复制、读写分离架构
3. **缓存集群** — 学习 Redis Sentinel 故障转移机制
4. **可观测性** — 搭建企业级监控体系
5. **网络架构** — 实践容器网络、跨子网通信

## 作者

Wang Jiong — Network Engineering, cloud computing enthusiast.

## License

MIT
