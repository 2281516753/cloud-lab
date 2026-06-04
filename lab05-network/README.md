# Lab 05: Custom Docker Networks

Multi-subnet container networking with isolated bridge networks and inter-subnet routing.

## Topology

```
10.0.1.0/24 (subnet-a)        10.0.2.0/24 (subnet-b)
┌────────────────────┐       ┌────────────────────┐
│ web-a  10.0.1.10   │       │ web-b  10.0.2.10   │
│ client-a 10.0.1.20 │       │ client-b 10.0.2.20 │
│ router 10.0.1.254──┼───────┼──10.0.2.254 router │
└────────────────────┘       └────────────────────┘
```

## Quick Start

```bash
docker compose up -d
docker compose ps
```

## Verify Network Isolation

```bash
# Within same subnet (works)
docker exec client-a ping -c 2 web-a

# Across subnets (requires routing setup on router)
docker exec router sysctl -w net.ipv4.ip_forward=1
docker exec client-a ping -c 2 10.0.2.10
```

## Experiments

1. **Isolation**: By default, hosts in subnet-a cannot reach subnet-b
2. **Routing**: Enable IP forwarding on router to connect both subnets
3. **DNS**: Test container name resolution within same network
4. **Capture**: `docker exec router tcpdump -i any` to observe traffic
