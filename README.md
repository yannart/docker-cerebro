## Description
Docker image to run cerebro elasticsearch web admin tool (replaces Kopf).

Cerebro project: https://github.com/lmenezes/cerebro

This Docker image is built in available in Docker hub `yannart/cerebro:latest`, see https://hub.docker.com/r/yannart/cerebro/

## Usage
To run the image:
`docker run -d -p 9000:9000 --name cerebro yannart/cerebro:latest`

Then you can access the web console in this URL: http://[Docker_Host]:9000

You can mount volumes for the configuration folder and / the logs, for example:

`docker run -d -p 9000:9000 --name cerebro -v /mount_folder/logs:/opt/cerebro-0.2.0/logs -v /mount_folder/conf:/opt/cerebro-0.2.0/conf yannart/cerebro:latest`

Where `/mount_folder` is a folder in the Docker host to contain the data. If mounted, the volume `/opt/cerebro-0.2.0/conf` must contain a valid configuration.

## Docker-compose example

The provided docker-compose project runs cerebro and a cluster 2 nodes with Elasticsearch 5.0.0.
Tu run it:
`docker-compose up -d`

Then you can access the web console in this URL: http://[Docker_Host]:9000 and connect to the Elasticsearch cluster using the URL `http://elasticsearch:9300` or `http://elasticsearch2:9301` in the hosts input field.
