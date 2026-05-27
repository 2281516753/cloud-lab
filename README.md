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

## 使用场景

**场景一：准备面试时快速搭建负载均衡实验环境**

面试中常被问到 Nginx 反向代理、负载均衡算法、健康检查等知识点。只需进入 `lab01-nginx-lb/` 目录执行 `docker compose up -d`，即可获得一个包含 Nginx 负载均衡器和多个后端服务的完整实验环境，随时验证配置、观察轮询/加权等调度策略的实际效果。

**场景二：教学演示中一键拉起完整监控栈**

讲师或助教在课堂上演示可观测性概念时，无需繁琐的软件安装和环境配置。进入 `lab04-monitoring/` 目录，一条命令即可启动 Prometheus + Grafana 监控栈，直接展示指标采集、仪表盘可视化和告警规则的全流程，学生也可以在自己的机器上复现。

**场景三：学习数据库高可用时零成本搭建 MySQL 主从集群**

MySQL 主从复制和读写分离是后端开发的必学内容。通过 `lab02-mysql-cluster/`，无需申请云资源或手动配置多台虚拟机，在本地 Docker 环境中即可模拟主库写入、从库同步、故障切换等场景，理解 binlog、复制延迟、数据一致性等核心概念。

**场景四：验证容器网络原理时快速创建多子网互联拓扑**

Docker 网络的 bridge、overlay、自定义子网等概念比较抽象。进入 `lab05-network/` 实验，自动创建多个自定义网络和子网，容器分布在不同网段中，可以通过 `docker exec` 进入容器实际测试跨子网连通性、DNS 解析和网络隔离效果。

## 作者

Wang Jiong — Network Engineering, cloud computing enthusiast.

## License

MIT
