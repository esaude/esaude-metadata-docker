<br/><br/><br/>
<img src="https://s3-eu-west-1.amazonaws.com/esaude/images/esaude-site-header.png" alt="OpenMRS"/>
<br/><br/><br/>

# eSaude EMR Metadata Docker


This repository contains the necessary infrastructure code and related resources
required to compose and run Docker containers that start an instance
of the eSaude Metadata.

For more information about eSaude Metadata visit [esaude.org](http://www.esaude.org/).

## Prerequisites

Make sure you have [Docker](https://docs.docker.com/) and [Docker Compose](https://docs.docker.com/compose/install/) installed.

## Setup

Start by cloning this repository and entering the directory:

````
https://github.com/esaude/esaude-metadata-docker.git
esaude-metadata-docker
````


### Building The Images

Run:

```
docker-compose build
```

### Initialization

Once the pulling or building is complete, you'll have to make sure that the mysql container
is initialized due to [this limitation](https://github.com/docker-library/mysql/issues/81).


run:

```
docker-compose up esaude-metadata-mysql
```

When you see the following, and nothing more is being logged to the console, it's done initializing:

```
Version: '5.6.29'  socket: '/var/run/mysqld/mysqld.sock'  port: 3306  MySQL Community Server (GPL)
```

You can then press <kbd>Ctrl+C</kbd> to stop the container. After this you can
run eSaude Metadata by executing the following:

```
docker-compose up
```

## Access

To log into eSaude Metadata, use the following details:

* **Host**: `DOCKER_HOST:8080/openmrs`
* **User**: admin
* **Pass**: eSaude123


## License

[MPL 2.0 w/ HD](http://openmrs.org/license/)