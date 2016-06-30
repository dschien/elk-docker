# Elasticsearch, Logstash, Kibana (ELK) Docker image - with Filebeat

# Deploy

`docker-compose up`

# Filebeat config
set env variable JSON_LOGFILES_DIR
## install template
`curl -XPUT 'http://elk:9200/_template/filebeat?pretty' -d@/etc/filebeat/filebeat.template.json`

*Note*: SSL is deactivated


### Documentation

See the [ELK Docker image documentation web page](http://elk-docker.readthedocs.io/) for complete instructions on how to use this image.

### Docker Hub

This image is hosted on Docker Hub at [https://hub.docker.com/r/sebp/elk/](https://hub.docker.com/r/sebp/elk/).

### About

Written by [Sébastien Pujadas](https://pujadas.net), released under the [Apache 2 license](https://www.apache.org/licenses/LICENSE-2.0).

