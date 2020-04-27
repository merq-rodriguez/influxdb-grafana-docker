
# InfluxDB and Grafana  with Docker

### 1. Create network

  ```
  $ docker network create monitoring
  ```

### 2. Create volume for grafana

```
  $ docker volume create grafana-volume
```

### 3. Create volume for influxdb
  ```
    $ docker volume create influxdb-volume
  ```


## Run docker command

 ```docker
 $ docker run --rm \
      -e INFLUXDB_DB=telegraf -e INFLUXDB_ADMIN_ENABLED=true \
      -e INFLUXDB_ADMIN_USER=admin \
      -e INFLUXDB_ADMIN_PASSWORD=supersecretpassword \
      -e INFLUXDB_USER=telegraf -e INFLUXDB_USER_PASSWORD=secretpassword \
      -v influxdb-volume:/var/lib/influxdb \
  influxdb /init-influxdb.sh
```

## Run docker compose
```bash
  $ docker-compose up -d
```