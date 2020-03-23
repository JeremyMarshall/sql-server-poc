# SQL Server POC

This is an example on how to run SQL SERVER in docker-compose

It Persists data to docker volumes and will survive restarts

## How to use

### Spin up the SQL Server instance

```
docker-compose up -d sql

# see logs
docker-compose logs sql --follow
```

or run it in the foreground

```
docker-compose up sql
```

### Run an SQL file in 

the working directory maps from `rawdata` to `/rawdata`

```
docker-compose run tools -i <file>
```

### Run an interactive session

```
docker-compose run tools

# ctrl-D to exit
# put "go" on its own line to run
```

## Connect to a tool on the host machine

Item | Value |
--- | --- |
server | `localhost` |
port | `1433` |
user | `sa` |
password | `P8ssw0rd` |

## Stop gracefully

```
docker-compose down

# ctrl-c if running in foreground
```

Let it complete to flush the transaction log

## Remove persisted data - start from scratch

```
docker volume rm sql-server_data sql-server_log
```


