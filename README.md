# Example Node/MySQL project

This project can be used as an example of starting multiple containers that depend on one another to create a database driven application.

## Run npm install

``` bash
npm install
```

## Create a place for the MySQL data

``` bash
mkdir -p ./data/db
```

## Populate mysql database

* Copy the contents of the `init.sql` file
* Navigate to http://localhost:30002
* Login with `root:root`
* Go to the `SQL` tab
* Paste contents of the `init.sql` file
* Click `Go`

## View database output

You now have output that you should see by navigating your browser to http://localhost:30001

## Shared data volume

You will notice that the data will be in your local db folder and represents the folder that can be designated for persistant data storage on a installed system

## Archiving containers

Using docker the resulting containers can be archived and transported to another operating system running Docker like this:

``` bash
docker image save oaklabs/example-node-mysql mysql node phpmyadmin/phpmyadmin | gzip -c > example-node-mysql.tar.gz
```

## Copy docker-compose.yml

Copy the docker-compose.yml to the remote docker Install and run

``` bash
docker-compose up --build
```

## Importing containers into remote Docker install

On your target docker install with Docker running , you can perform this command to install the containers into a new docker install.

``` bash
gunzip -c example-node-mysql.tar.gz | docker load
```
