# BI-SP2 Frontend

As mentioned before, we use Nette, PHP based web framework. Currently, app requires at least PHP 7.0.

## Setup

Best way to get frontend part working is using attached docker-compose file.
```shell
# here should be the docker-compose.yml file
cd $PATH_TO_YOUR_PROJECT_FOLDER

# clone repo to local project folder
git clone git@.... project

# make project your working directory
cd project

# run containers
docker-compose up -d
```

## Run custom commands

Sometimes, you have to do some *dirty* commands directly in containers. Use following commands to access container shell.
```shell
# open interactive shell in php container
# project is mounted in /var/www/html
docker-compose exec web bash

# or

# open interactive shell in mariadb container
# project is mounted to /var/shared_data
docker-compose exec mariadb bash
```

## Web access

You can run the whole app (even tests) on your local machine on `http://localhost:8080/www`. DB is **not** accessible directly from host.
