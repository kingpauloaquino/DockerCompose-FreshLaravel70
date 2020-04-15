# DockerCompose-NoLaravel
A pretty simplified docker-compose workflow that sets up a LEMP network of containers for local Laravel development.

## Usage

To get started, make sure you have [Docker installed](https://docs.docker.com/docker-for-mac/install/) on your system, and then clone this repository.

Your entire Laravel project located to `src` folder, then open a terminal and from this cloned respository's root run `docker-compose up -d --build`. Open up your browser of choice to [http://localhost:8080](http://localhost:8080) and you should see your Laravel app running as intended. **Your Laravel app needs to be in the src directory first before bringing the containers up, otherwise the artisan container will not build, as it's missing the appropriate file.** 

**New:** Three new containers have been added that handle Composer, NPM, and Artisan commands without having to have these platforms installed on your local computer. Use the following command templates from your project root, modifiying them to fit your particular use case:

- `docker-compose up -d --build` - To start and run in the background
- `docker-compose up --force-recreate` - To start, rebuilding and show the logs
- `docker-compose down -v` - To stop, remove container
- `docker-compose run --rm composer update`
- `docker-compose run --rm npm run dev`
- `docker-compose run --rm artisan migrate` 

Containers created and their ports (if used) are as follows:

- **nginx** - `:8080`
- **mysql** - `:3306`
- **php** - `:9000`
- **npm**
- **composer**
- **artisan**

## NGINX
To change the `vhost file` go to nginx folder

## PHP
To change the `php.ini` go to config folder and edit `php.ini` - you need to re-build your container to take effect.

## MySQL
Your MySQL Database Store to mysql folder. To change the `my.cnf` go to config folder and edit `my.cnf` - you need to re-build your container to take effect. `Note: Before you start this container/docker, make sure that the my_data folder is empty.`
