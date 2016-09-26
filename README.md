## Description
Docker image to run cerebro elasticsearch web admin tool (replaces Kopf).

Cerebro project: https://github.com/lmenezes/cerebro

This Docker image is built in available in Docker hub `yannart/cerebro:latest`, see https://hub.docker.com/r/yannart/cerebro/

## Usage
To run the image:
`docker run -p 9000:9000 yannart/cerebro:latest`

Then you can access the web console in this URL: http://[Docker Host]:9000

## Docker-compose example

The provided docker-compose project runs cerebro and a cluster 2 nodes with Elasticsearch 5.0.0.
Tu run it:
`docker-compose up -d`

Then you can access the web console in this URL: http://[Docker Host]:9000 and connect to the Elasticsearch cluster using the URL `http://elasticsearch:9300` or `http://elasticsearch2:9301` in the hosts input field.
