# Docker for Symfony

A sample starting point docker for a Symfony project
It has php 8, 

## Requirements
* docker and docker-compose


## Installation

* Clone the repository

* Install the containers:

move to the "docker" folder

```sh
docker-compose -f docker-compose.yml -f pma.yml build

```

* Run the containers
wait for the installation to finish then run the following command to start the containers

```sh
docker-compose -f docker-compose.yml -f pma.yml up
```

That command runs the php, nginx, mysql and pma container, if you don't need the database interface you can the "-f pma.yml"

* Install symfony:
connect to the shell php container

```sh
docker exec -it test-php sh
```

once inside the pho container shell, install symfony via composer

```sh
composer create-project symfony/skeleton:"6.3.*"
```

the previous command is enough if you are building a microservice, otherwise install the different traditional web application dependencies

```sh
composer require webapp
```

* Test
Head over http://127.0.0.1:8011/
And to for the datbase http://127.0.0.1:4011/
