## About Project

Dockerize PHP Laravel Postgresql Redis 

## Technologies
- PHP 7.3
- Laravel 8
- PostgreSql 12.2
- Docker
- Redis

## Installation Process
* Docker is available in this project. Please install Docker before start. Click [here](https://www.docker.com/) to know about Docker. For installation guide please follow [this](https://www.docker.com/get-started) link.*
- __Step 1:__ Clone this project `https://github.com/jasimjuwel/dockerize-laravel-postgresql-redis.git` form here. 
- __Step 2:__ put this docker files into laravel project
- __Step 3:__ Now create environment file
    > cp .env.example .env
- __Step 4:__ configure .env
    >  vim .env

        APP_NAME=testapp
        DB_CONNECTION=pgsql
        DB_HOST=172.10.1.5
        DB_PORT=5432
        DB_DATABASE=test_app_db
        DB_USERNAME=postgres
        DB_PASSWORD=123456
- 
        CACHE_DRIVER=redis
- 
        REDIS_CLIENT=predis
        REDIS_HOST=172.10.1.2
        REDIS_PASSWORD=null
        REDIS_PORT=6379
- 
        UID=1000
- 
- __Step 5:__ run docker-compose build
    > docker-compose up --build
- __Step 6:__ run docker-compose up in detach mode
    > docker-compose up -d
- __Step 7:__ Now login into workspace container for application setup
    > docker exec -ti -u suser testapp bash
- __Step 8:__ Download laravel dependencies 
    > composer install
- __Step 9:__ Now create environment key for laravel
    > php artisan key:generate
- __Step 10:__ clear the config cache
    > php artisan config:cache
- 
    > php artisan view:clear
- 
    > php artisan route:clear
- 
    > composer dump -o
- __Step 11:__ run migration
  > php artisan migrate
- __Step 12:__ Now browse http://172.10.1.7/ for application
- __Step 13:__ Accessing Redis from terminal
  > docker exec -ti testapp-redis /bin/sh
- 
  > redis-cli
- 
  > ping
- __Step 14:__ Pgadmin & postgresql credintials
  - 
- 
      pagadmin url : 172.10.1.4
  - 
      user : admin@pgadmin.com
  - 
      pass : 123456
- 
      postgresql server ip : 172.10.1.5
      postgresql server database : test_app_db
      postgresql server user : postgres
      postgresql server pass : 123456

#### Feel free inform me for any help. email : jasimjuwel0@gmail.com


