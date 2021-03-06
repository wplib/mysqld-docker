![MySQL 8.0.x](https://img.shields.io/badge/MySQL-8.0.x-green.svg)
![MySQL 5.7.x](https://img.shields.io/badge/MySQL-5.7.x-green.svg)
![MySQL 5.6.x](https://img.shields.io/badge/MySQL-5.6.x-green.svg)
![MySQL 5.5.x](https://img.shields.io/badge/MySQL-5.5.x-green.svg)

![WPLib-Box](https://github.com/wplib/wplib.github.io/raw/master/WPLib-Box-100x.png)


# MySQL Docker Container for WPLib Box
This is the repository for the [mysql-docker](https://www.mysql.com/) Docker container implemented for [WPLib-Box](https://github.com/wplib/wplib-box).
It currently provides versions 5.5.x 5.6.x 5.7.x 8.0.x


## Supported tags and respective Dockerfiles

`8.0.11`, `8.0` _([8.0.11/Dockerfile](https://github.com/wplib/mysql-docker/blob/master/8.0.11/Dockerfile))_

`5.7.22`, `5.7`, `latest` _([5.7.22/Dockerfile](https://github.com/wplib/mysql-docker/blob/master/5.7.22/Dockerfile))_

`5.6.40`, `5.6` _([5.6.40/Dockerfile](https://github.com/wplib/mysql-docker/blob/master/5.6.40/Dockerfile))_

`5.5.60`, `5.5` _([5.5.60/Dockerfile](https://github.com/wplib/mysql-docker/blob/master/5.5.60/Dockerfile))_


## Using this container.
If you want to use this container as part of WPLib, then use the Docker Hub method.
Or you can use the GitHub method to build and run the container.


## Using it from Docker Hub

### Links
(Docker Hub repo)[https://hub.docker.com/r/wplib/mysql/]

(Docker Cloud repo)[https://cloud.docker.com/swarm/wplib/repository/docker/wplib/mysql/]


### Setup from Docker Hub
A simple `docker pull wplib/mysql` will pull down the latest version.


### Runtime from Docker Hub
start - Spin up a Docker container with the correct runtime configs.

`docker run -d --name wplib_mysql_8.0.11 --restart unless-stopped --network wplibbox -p 3306:3306 -v /projects/wplib.box/sql:/docker-entrypoint-initdb.d -v mysql_data:/var/lib/mysql wplib/mysql:8.0.11`

stop - Stop a Docker container.

`docker stop wplib_mysql_8.0.11`

run - Run a Docker container in the foreground, (all STDOUT and STDERR will go to console). The Container be removed on termination.

`docker run --rm --name wplib_mysql_8.0.11 --network wplibbox -p 3306:3306 -v /projects/wplib.box/sql:/docker-entrypoint-initdb.d -v mysql_data:/var/lib/mysql wplib/mysql:8.0.11`

shell - Run a shell, (/bin/bash), within a Docker container.

`docker run --rm --name wplib_mysql_8.0.11 -i -t --network wplibbox -p 3306:3306 -v /projects/wplib.box/sql:/docker-entrypoint-initdb.d -v mysql_data:/var/lib/mysql wplib/mysql:8.0.11 /bin/bash`

rm - Remove the Docker container.

`docker container rm wplib_mysql_8.0.11`


## Using it from GitHub repo

### Setup from GitHub repo
Simply clone this repository to your local machine

`git clone https://github.com/wplib/mysql-docker.git`


### Building from GitHub repo
`make build` - Build Docker images. Build all versions from the base directory or specific versions from each directory.


`make list` - List already built Docker images. List all versions from the base directory or specific versions from each directory.


`make clean` - Remove already built Docker images. Remove all versions from the base directory or specific versions from each directory.


`make push` - Push already built Docker images to Docker Hub, (only for WPLib admins). Push all versions from the base directory or specific versions from each directory.


### Runtime from GitHub repo
When you `cd` into a version directory you can also perform a few more actions.

`make start` - Spin up a Docker container with the correct runtime configs.


`make stop` - Stop a Docker container.


`make run` - Run a Docker container in the foreground, (all STDOUT and STDERR will go to console). The Container be removed on termination.


`make shell` - Run a shell, (/bin/bash), within a Docker container.


`make rm` - Remove the Docker container.


`make test` - Will issue a `stop`, `rm`, `clean`, `build`, `create` and `start` on a Docker container.


