## MariaDB 10 server on Alpine

[![](https://images.microbadger.com/badges/image/wrightie/alpine-mariadb.svg)](https://microbadger.com/images/wrightie/alpine-mariadb "Get your own image badge on microbadger.com")

## Credits

This image was cloned from [nimmis/alpine-mariadb](https://hub.docker.com/r/nimmis/alpine-mariadb/) and updated for internal use to match the it_IT locale, removing some unused build labels; also, it was fixed to let you run a new container reusing previously saved volume data.

## What is MariaDB?

MariaDB is a community-developed fork of the MySQL relational database management system intended to remain free under the GNU GPL.


Container based on **nimmis/alpine-micro** [![Docker Hub; nimmis/alpine-micro](https://images.microbadger.com/badges/image/nimmis/alpine-micro.svg)](https://hub.docker.com/r/nimmis/alpine-micro/), a minimal os (8.5 Mb)  with working init process and syslog. For more information on how to set up services, please read the documentation for [nimmis/alpine-micro](https://registry.hub.docker.com/u/nimmis/alpine-micro). This container is about half the size of the official MariaDB docker container.


## Starting the container

To run the lastest stable version of this docker image run

	docker run -d -e MARIADB_RANDOM_ROOT_PASSWORD=yes wrightie/alpine-mariadb

to expose the database to the external interface run

	docker run -d -p 3306:3306 e MARIADB_RANDOM_ROOT_PASSWORD=yes wrightie/alpine-mariadb

## Environment variables used in the container

### MARIADB_ROOT_PASSWORD
This variable defines the password for the root user in the database, se it with

	-e MARIADB_ROOT_PASSWORD=secretpassword

add quotes if there is spaces or other special character in the password

	-e MARIADB_ROOT_PASSWORD='password with spaces'

### MARIADB_RANDOM_ROOT_PASSWORD
This variable generate a random password for the root user, add 

	-e MARIADB_RANDOM_ROOT_PASSWORD=yes

The password can then be found by looking at the log output

	docker logs <container>

### MARIADB_ALLOW_EMPTY_PASSWORD
This allowes the root password to be blank (remember: **THIS IS A MAJOR SECURITY RISK**); add

	-e MARIADB_ALLOW_EMPTY_PASSWORD=yes

### MARIADB_REMOTE_ROOT
Normally the root user can only use localhost to access the databases; adding

	-e MARIADB_REMOTE_ROOT=yes

allows root access from any host

### MARIADB_DATABASE
Creates a database with the defined name

	-e MARIADB_DATABASE=databasename

### MARIADB_USER
Creates a user with password defined with MARIADB_PASSWORD and full access to the database defined by MARIADB_DATABASE

	-e MARIADB_USER=username

### MARIADB_PASSWORD
The password for the user defined by MARIADB_USER

	-e MARIADB_PASSWORD=donottell


## Volumes

The /data volume is defined containing

### /data/conf

Contains the configuration of MariaDB (**my.cnf**)

### /data/db

Contains the database files

### /data/logs

Contains logs from MariaDB
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk2NTc4ODcxMF19
-->
