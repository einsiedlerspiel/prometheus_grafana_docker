[![Docker Compose](https://github.com/einsiedlerspiel/prometheus_grafana_docker/actions/workflows/push.yml/badge.svg)](https://github.com/einsiedlerspiel/prometheus_grafana_docker/actions/workflows/push.yml)

# A Docker Stack which sets up Prometheus and Grafana
Here's a quick start to stand-up a Docker [Prometheus](http://prometheus.io/) stack containing Prometheus, Grafana.

## Pre-requisites
Before we get started installing the Prometheus stack. Ensure you install the latest version of docker and [docker-compose](https://docs.docker.com/compose/install/) on your Docker host machine. This has also been tested with Docker for Mac and it works well.

## Installation
Clone the project to your Docker host.

If you would like to change which targets should be monitored or make configuration changes edit the [/prometheus/prometheus.yml](https://github.com/vegasbrianc/prometheus/blob/version-2/prometheus/prometheus.yml) file. The targets section is where you define what should be monitored by Prometheus. The names defined in this file are actually sourced from the service name in the docker-compose file. If you wish to change names of the services you can add the "container_name" parameter in the `docker-compose.yml` file.

## Configuration

Once configurations are done let's start it up. From the /prometheus project directory run the following command:

    $ docker-compose up -d


That's it. docker-compose builds the entire Grafana and Prometheus stack automagically.

The Grafana Dashboard is now accessible via: `http://<Host IP Address>:3000` for example http://192.168.10.1:3000

username - admin password - foobar (Password is stored in the `config.monitoring` env file)

The DataSource and Dashboard for Grafana are automatically provisioned. You can still install the dashboard manually if you choose below.


<center><img src="https://github.com/vegasbrianc/github-monitoring/blob/master/images/Grafana_Add_Data_Source.png" width="400" heighth="400"></center>

## Thanks

The basic set up is based on [@vegasbrianc](https://github.com/vegasbrianc) great [docker stack for running prometheus and grafana](https://github.com/vegasbrianc/github-monitoring)

The bits relating to airgradient are taken from Jeff Geerlings [InternetPi project](https://github.com/geerlingguy/internet-pi)
