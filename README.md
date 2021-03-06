# Docker-compose files for a simple uptodate
# InfluxDB
# + Grafana stack
# + Telegraf

Get the stack (only once):

```
git clone https://github.com/superadmin88/docker-influxdb-telegraf-grafana
cd docker-influxdb-grafana
docker pull grafana/grafana
docker pull influxdb
docker pull telegraf
```

Run your stack:

```
docker-compose config
docker-compose pull
docker-compose up -d
```

Show me the logs:

```
docker-compose logs
```

Stop it:

```
docker-compose stop
docker-compose rm
```

Update it:

```
git pull
docker pull grafana/grafana
docker pull influxdb
docker pull telegraf
```

If you want to run Telegraf, edit the telegraf.conf to yours needs and:

```
docker exec telegraf telegraf
```
Testing telegraf at influxdb
```
docker exec -it influxdb bash
influx
show databases
use telegraf
select * from cpu where time > now() - 30s
```
Images sizes:
```
docker image ls
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
grafana/grafana     latest              a8b0c77b00b7        25 hours ago        245MB
influxdb            latest              4ca83dc311a6        13 days ago         239MB
telegraf            latest              2133a07c3185        2 weeks ago         244MB
```
