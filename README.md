# Elasticsearch, Logstash, Kibana (ELK) Docker image - with Filebeat

# Deploy

`docker-compose up`

# Filebeat config
set env variable JSON_LOGFILES_DIR
## install template
`curl -XPUT 'http://elk:9200/_template/filebeat?pretty' -d@/etc/filebeat/filebeat.template.json`

*Note*: SSL is deactivated


# Debug
## Start elk by itself
`JSON_LOGFILES_DIR=. docker-compose up elk`

## Login to elk
`JSON_LOGFILES_DIR=. docker-compose exec elk bash`
## Stop Logstash
`service logstash stop`

## Start with debug config
`/opt/logstash/bin/logstash -f /etc/logstash/debug-conf.d


### Documentation

See the [ELK Docker image documentation web page](http://elk-docker.readthedocs.io/) for complete instructions on how to use this image.

### Docker Hub

This image is hosted on Docker Hub at [https://hub.docker.com/r/sebp/elk/](https://hub.docker.com/r/sebp/elk/).

### About

Written by [Sébastien Pujadas](https://pujadas.net), released under the [Apache 2 license](https://www.apache.org/licenses/LICENSE-2.0).

