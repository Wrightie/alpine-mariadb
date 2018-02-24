---


---

<h2 id="mariadb-10-server-on-alpine">MariaDB 10 server on Alpine</h2>
<p><a title="Get your own image badge on microbadger.com" href="https://microbadger.com## MariaDB 10 server on Alpine

[![](https://images.microbadger.com/badges/images/wrightie/alpine-mariadb"><img alt="" src=".svg)](https://images.microbadger.com/badges/images/wrightie/alpine-mariadb.svg"></a></p>
<h2 id="credits">Credits</h2>
<p> "Get your own image badge on microbadger.com")

## Credits

This image was cloned from <a href="[nimmis/alpine-mariadb](https://hub.docker.com/r/nimmis/alpine-mariadb/">nimmis/alpine-mariadb</a>) and updated for internal use to match the it_IT locale, removing some unused build labels.  ; also, it was fixed to let you run a new container reusing previously saved volume data.</p>
<h2 id="what-is-mariadb">

## What is MariaDB?</h2>
<p>

MariaDB is a community-developed fork of the MySQL relational database management system intended to remain free under the GNU GPL.</p>
<p>


Container based on <strong>nimmis/alpine-micro</strong> <a href="https://hub.docker.com/r/**nimmis/alpine-micro/"><img alt="** [![Docker Hub; nimmis/alpine-micro" src="](https://images.microbadger.com/badges/image/nimmis/alpine-micro.svg"></a>)](https://hub.docker.com/r/nimmis/alpine-micro/), a minimal os (8.5 Mb)  with working init process and syslog. For more information on how to set upp services, please read the dockumentation for <a href="[nimmis/alpine-micro](https://registry.hub.docker.com/u/nimmis/alpine-micro">nimmis/alpine-micro</a>). This container is about half the size of the official mMariadbDB docker container.</p>
<h2 id="starting-the-container">


## Starting the container</h2>
<p>

To run the lastest stable version of this docker image run</p>
<pre><code>

	docker run -d -e MARIADB_RANDOM_ROOT_PASSWORD=yes nimmiswrightie/alpine-mariadb
</code></pre>
<p>
to expose the database to the external interface run</p>
<pre><code>

	docker run -d -p 3306:3306 e MARIADB_RANDOM_ROOT_PASSWORD=yes nimmiswrightie/alpine-mariadb
</code></pre>
<h2 id="environment-variables-used-in-the-container">
## Environment variables used in the container</h2>
<h3 id="mariadb_root_password">

### MARIADB_ROOT_PASSWORD</h3>
<p>
This variable defines the password for the root user in the database, se it with</p>
<pre><code>

	-e MARIADB_ROOT_PASSWORD=secretpassword
</code></pre>
<p>
add quotes if there is spaces or other special character in the passwordd</p>
<pre><code>

	-e MARIADB_ROOT_PASSWORD='password with spaces'
</code></pre>
<h3 id="mariadb_random_root_password">
### MARIADB_RANDOM_ROOT_PASSWORD</h3>
<p>
This variable generate a random password for the root user, add</p>
<pre><code> 

	-e MARIADB_RANDOM_ROOT_PASSWORD=yes
</code></pre>
<p>
the password can then be found by looking at the log output</p>
<pre><code>

	docker logs &lt;<container&gt;
</code></pre>
<h3 id="mariadb_allow_empty_password">>

### MARIADB_ALLOW_EMPTY_PASSWORD</h3>
<p>
This allowes the root password to be blank, (remember: <strong>**THIS IS A MAJOR SECURITY RISK,</strong>); add</p>
<pre><code>**); add

	-e MARIADB_ALLOW_EMPTY_PASSWORD=yes
</code></pre>
<h3 id="mariadb_remote_root">
### MARIADB_REMOTE_ROOT</h3>
<p>
Normally the root user can only use localhost to access the databases; adding</p>
<pre><code>

	-e MARIADB_REMOTE_ROOT=yes
</code></pre>
<p>
allows root access from any host</p>
<h3 id="mariadb_database">

### MARIADB_DATABASE</h3>
<p>
cCreates a database with the defined name</p>
<pre><code>

	-e MARIADB_DATABASE=databasename
</code></pre>
<h3 id="mariadb_user">
### MARIADB_USER</h3>
<p>
cCreates a user with password defined with MARIADB_PASSWORD and full access to the database defined by MARIADB_DATABASE</p>
<pre><code>

	-e MARIADB_USER=username
</code></pre>
<h3 id="mariadb_password">
### MARIADB_PASSWORD</h3>
<p>
The apassword for the user defined by MARIADB_USER</p>
<pre><code>

	-e MARIADB_PASSWORD=donottell
</code></pre>
<h3 id="mariadb_password-1">MARIADB_PASSWORD</h3>
<h2 id="volumes">Volumes</h2>
<p>## Volumes

The /data volume is defined containing</p>
<h3 id="dataconf">

### /data/conf</h3>
<p>

Contains the configuration of mMariadbDB (<strong>my.cnf</strong>)</p>
<h3 id="datadb">/data/db</h3>
<p>**my.cnf**)

### /data/db

Contains the database files</p>
<h3 id="datalogs">

### /data/logs</h3>
<p>

Contains logs from mMariadbDB</p>

<!--stackedit_data:
eyJoaXN0b3J5IjpbNDc5MDQyOTM3XX0=
-->