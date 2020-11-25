# Example Node/MySQL project

This project can be used as an example of starting multiple containers that depend on one another to create a database driven application.

## Run npm install

``` bash
npm install
```

## Build docker containers

``` bash
docker-compose up --build
```

## Populate mysql database

* Create a place for the MySQL data to go in your local project folder

``` bash
mkdir -p ./data/db
```

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

