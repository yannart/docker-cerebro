## Description
Docker image to run cerebro [Elasticsearch 5.x](https://www.elastic.co/products/elasticsearch) web admin tool that replaces [Kopf](https://github.com/lmenezes/elasticsearch-kopf).

Cerebro project: https://github.com/lmenezes/cerebro

This Docker image is built and available in Docker hub [yannart/cerebro:latest](https://hub.docker.com/r/yannart/cerebro/)

### Docker Tags

`yannart/cerebro` provides multiple tagged images:

* `latest` (default): Latest version of Cerebro.
* `0.4.2`: Cerebro 0.4.2

## Usage
To run the image:
`docker run -d -p 9000:9000 --name cerebro yannart/cerebro:latest`

Then you can access the web console in this URL: http://[Docker_Host]:9000

You can mount volumes for the configuration folder and / the logs, for example:

`docker run -d -p 9000:9000 --name cerebro -v /mount_folder/logs:/opt/cerebro-0.4.2/logs -v /mount_folder/conf:/opt/cerebro-0.4.2/conf yannart/cerebro:latest`

Where `/mount_folder` is a folder in the Docker host to contain the data. If mounted, the volume `/opt/cerebro-0.4.2/conf` must contain a valid configuration.

## Docker-compose example

A docker-compose project is available in the [GitHub](https://github.com/yannart/docker-cerebro) project to run cerebro and a cluster 2 nodes with Elasticsearch 5.1.1.
To run it:
`docker-compose up -d`

Then you can access the web console in this URL: http://[Docker_Host]:9000 and connect to the Elasticsearch cluster using the URL `http://elasticsearch:9200` or `http://elasticsearch2:9201` in the hosts input field.
