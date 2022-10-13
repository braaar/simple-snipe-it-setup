# simple-snipe-it-setup
This repo contains the basic necessities for getting [snipe-it](https://github.com/snipe/snipe-it) up and running, using docker images from the helpful folks at [linuxserver.io](https://www.linuxserver.io/)

SnipeIT is an asset management system built with PHP and serves a browser-based GUI. It uses MySQL or MariaDB to store data. This setup includes both the snipeIT server and the database server.
# Prerequisites

You must have Docker and docker compose installed. You must also be running one of the supported architectures for the  [snipe-it image](https://github.com/linuxserver/docker-snipe-it#supported-architectures) and the [mariadb image](https://github.com/linuxserver/docker-mariadb#supported-architectures).

See [Linuxserver's guide to docker compose](https://docs.linuxserver.io/general/docker-compose) if you are new to this.

# Run server

To run SnipeIT, simply run

```sh
docker compose up
```

Then you can open up `http://localhost:8081` and go through SnipeIT's setup in the Web UI to get things running. 
After that you will be able to use the software, but only if you have access to the local machine. Further setup is required for hosting this in an actual environment.
# Secrets

Secrets can be managed using [Docker secrets](https://docs.docker.com/engine/swarm/secrets/).

`db_password` and `db_root_password` have been set up in this repo so far. There are other config variables that should probably be set up through secrets, such as snipeIT's email configuration for system emails. See [linuxserver's documentation for environment variables](https://hub.docker.com/r/linuxserver/snipe-it#:~:text=arm32v7%2D%3Cversion%20tag%3E-,Application%20Setup,-Access%20the%20webui)
