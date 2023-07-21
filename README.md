# Watchdog


Deploy Prometheus Stack on Docker using docker compsoe.


## Diagram

![](assets/img/diagram.png)


## How To Run


- Clone the repo
```bash
$ git clone https://github.com/AhmedMattar21/watchdog.git
```

- Use Docker Compose to run the stack
```bash
$ cd watchdog

$ docker compose up -d --force-recreate
```


- Run the targets
```
$ cd targets

$ docker compose up -d
```


- Check deployed containters
```
$ docker ps
```

 
 
## How To Use

To access Prometheus:

- Open your browser on `localhost:9090`

To access Grafana:

- Open your browser on `localhost:3000`

- Login into Grafana using USERNAME: *admin* and PASSWORD: *watchdog*

and the same for Alertmanager and Pushgateway with replacing the port number.



## Grafana Dashboards

**1- Mysql Dashboard:** Runs without any extra configuration.

**2- Nodes Dashboard:** Needs to edit Prometheus configuration file to add your Nodes addresses and Exporter Port.

Edit Prometheus file to add your own targets.
```
$ nano ./prometheus/prometheus.yml 
```

```yaml

  - job_name: "Nodes"
    static_configs:
      - targets: ["192.168.1.8:9100","192.168.1.208:9100"]

```

NOTE: Recreate the stack to update the config files
```
$ docker compose up -d --force-recreate
```


**3- Docker-Engine Dashboard:** Needs to configure docker deamon and install Grafana-loki Plugin.

```

```




## Alerts





## Slack Integration

