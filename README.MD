# cloudops-elasticsearch-index-pruner

Docker image for cleaning up old indices, based on the [curator](https://github.com/elastic/curator) component.

[![Docker Automated build](https://img.shields.io/docker/automated/stena/cloudops-elasticsearch-index-pruner.svg?style=for-the-badge)](https://hub.docker.com/r/stena/cloudops-elasticsearch-index-pruner/)
[![Docker Build Status](https://img.shields.io/docker/build/stena/cloudops-elasticsearch-index-pruner.svg?style=for-the-badge)](https://hub.docker.com/r/stena/cloudops-elasticsearch-index-pruner/)
[![MicroBadger Size](https://img.shields.io/microbadger/image-size/stena/cloudops-elasticsearch-index-pruner.svg?style=for-the-badge)](https://hub.docker.com/r/stena/cloudops-elasticsearch-index-pruner/)
[![Docker Pulls](https://img.shields.io/docker/pulls/stena/cloudops-elasticsearch-index-pruner.svg?style=for-the-badge)](https://hub.docker.com/r/stena/cloudops-elasticsearch-index-pruner/)

## Configuration

Environment Variable  | Description                                                 | Default   | Required
----------------------|-------------------------------------------------------------|-----------|---------
ES_HOST               | The hostname of Elasticsearch                               | -         | true
ES_PORT               | The port of Elasticsearch                                   | -         | true
ES_BASIC_AUTH         | Username and password used when connecting to Elasticsearch | -         | false
INDEX_OLDER_THAN_DAYS | Indices older than this value will be deleted               | 14        | false
INDEX_PREFIX          | Indices matching the given prefix will be deleted           | logstash- | false

## Using the docker image

```bash
docker run --rm \
  -e ES_HOST=es_host \
  -e ES_PORT=es_port \
  -e ES_BASIC_AUTH=username:password \
  -e INDEX_OLDER_THAN_DAYS=index_older_than_days \
  -e INDEX_PREFIX=index_prefix \
  stena/cloudops-elasticsearch-index-pruner
```
