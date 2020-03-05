# Docker-Cantaloupe

Forked from: https://github.com/lyrasis/docker-cantaloupe/

Provides a basic docker container for 🍈 with all the image tools installed. Based on the [Ubuntu 18.04 image](https://hub.docker.com/_/ubuntu/).

## Environment Variables

### User

Inside the container Cantaloupe is run as a user named *Cantaloupe*. The UID and GID of this user can be controlled by setting the following environment variables:

* `CANTALOUPE_UID`
* `CANTALOUPE_GID`

Both of these default to 999. 

### Java

The arguements passed to Java when starting Cantaloupe can be controlled with:

* `JAVA_OPTS`

Default: `-Xmx500m`

### Cantaloupe.properties

The path that cantaloupe looks for *cantaloupe.properties* is configured by: 

* `PROPERTIES_FILE`. 

Default: `/cantaloupe/cantaloupe.properties`

You can change this if you want to mount your own cantaloupe.properties inside of the container. By default almost all of the cantaloupe.properties configuration is customized using environment variables. You can find the details of the environment variables you can set [here](cantaloupe.properties).  

`docker build -t cantaloupe .`

## Paths

Most of the paths are customizable using environment variables, but by default they are all located in `/cantaloupe`:
* Cache: `/cantaloupe/cache`
* Logs: `/cantaloupe/logs`
* Image Source: `/cantaloupe/images`

## Docker Compose Example

See `docker-compose.yml`. 
