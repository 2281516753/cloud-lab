# Lab 03: Redis Sentinel High Availability

Redis 7 HA cluster with Sentinel: 1 master + 2 replicas + 3 sentinels.

## Architecture

```
       ┌──────────────┐
       │ Sentinel × 3  │  (quorum = 2)
       └──────┬───────┘
              │ monitor
    ┌─────────┼─────────┐
    │         │         │
┌───▼──┐ ┌───▼──┐ ┌───▼──┐
│Master│ │Rep-1 │ │Rep-2 │
│:6379 │ │:6379 │ │:6379 │
└──────┘ └──────┘ └──────┘
```

## Quick Start

```bash
docker compose up -d
docker compose ps
```

## Verify

```bash
# Check master
docker exec redis-master redis-cli -a redis123 INFO replication | grep role

# Check sentinel
docker exec sentinel-1 redis-cli -p 26379 SENTINEL master mymaster

# Write to master
docker exec redis-master redis-cli -a redis123 SET testkey "hello"

# Read from replica
docker exec redis-replica-1 redis-cli -a redis123 GET testkey
```

## Test Failover

```bash
# Stop master
docker stop redis-master

# Watch sentinel election
docker exec sentinel-1 redis-cli -p 26379 SENTINEL master mymaster

# A replica will be promoted (within ~5s)
sleep 10
docker exec redis-replica-1 redis-cli -a redis123 INFO replication | grep role
```
