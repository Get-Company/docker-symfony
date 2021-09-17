# Get Structure

    git clone https://github.com/Get-Company/docker-symfony.git  YOUR_DIRECTORY

    cd YOUR_DIRECTORY

## Install containers
    docker-compose up -d --build

## Bash
    docker exec -it php74-container bash

### Install Symfony Project
    composer create-project symfony/skeleton .

### Doctrine
    composer require doctrine

### .env
    DATABASE_URL="mysql://root:secret@mysql8-service:3306/symfony_docker?serverVersion=8.0"

### Create DB

    php bin/console doctrine:database:create

## Adminer
    Credentials look at Mysql