# Lab 02: MySQL Master-Slave Cluster

MySQL 8.0 master-slave replication with ProxySQL read/write splitting.

## Architecture

```
App → ProxySQL (:6033) → Master (write)
                       → Slave  (read)
```

## Quick Start

```bash
docker compose up -d
docker compose ps
```

## Setup Replication (after containers are running)

```bash
# On master
docker exec -it mysql-master mysql -uroot -proot123 -e "
CREATE USER 'repl'@'%' IDENTIFIED BY 'repl123';
GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%';
FLUSH PRIVILEGES;
SHOW MASTER STATUS;
"

# On slave (use master status from above)
docker exec -it mysql-slave mysql -uroot -proot123 -e "
CHANGE MASTER TO
  MASTER_HOST='mysql-master',
  MASTER_USER='repl',
  MASTER_PASSWORD='repl123',
  MASTER_LOG_FILE='mysql-bin.000003',
  MASTER_LOG_POS=0,
  GET_MASTER_PUBLIC_KEY=1;
START SLAVE;
SHOW SLAVE STATUS\G
"
```

## Verify

```bash
# Write to master
docker exec -it mysql-master mysql -uroot -proot123 testdb -e "
CREATE TABLE test (id INT, val VARCHAR(20));
INSERT INTO test VALUES (1, 'hello');
"

# Read from slave
docker exec -it mysql-slave mysql -uroot -proot123 testdb -e "SELECT * FROM test;"
```

## ProxySQL Admin

```bash
mysql -h127.0.0.1 -P6032 -uadmin -padmin
```
