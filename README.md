# grafana-deployment



## Files 
* docker-compose.yml
  * Docker compose file to deploy 3 services
    * muirwoods-loki
    * muirwoods-repo-log-collector-promtail
    * muirwoods-grafana
  * Docker Network
    * loki
* grafana.ini
  * Grafana configuration file
* config.yml
  * Promtail configuration file
* local-config.yaml
  * Loki default configuration file

## Default Configuration
* Data Directory
  * ```${HOME}/data```
    * granana
    * loki

## How to Deploy
* Run ```docker compose up -d```
```shell   
group.np_app_hub@eve:~/work/grafana-deployment$ docker compose ps
NAME                                                     IMAGE                    COMMAND                  SERVICE                             CREATED             STATUS              PORTS
grafana-deployment-muirwoods-grafana-1                       grafana/grafana:latest   "sh -euc 'mkdir -p /…"   muirwoods-grafana                       9 days ago          Up 9 days           0.0.0.0:33000->3000/tcp, :::33000->3000/tcp
grafana-deployment-muirwoods-loki-1                          grafana/loki:2.9.2       "/usr/bin/loki -conf…"   muirwoods-loki                          9 days ago          Up 9 days           0.0.0.0:33100->3100/tcp, :::33100->3100/tcp
grafana-deployment-muirwoods-repo-log-collector-promtail-1   grafana/promtail:2.9.2   "/usr/bin/promtail -…"   muirwoods-repo-log-collector-promtail   9 days ago          Up 9 days
group.np_app_hub@eve:~/work/grafana-deployment$
```
