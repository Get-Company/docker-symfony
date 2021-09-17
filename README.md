# Get Structure

git clone https://github.com/GaryClarke/nginx-php7.4-mysql8-node-docker-network.git YOUR_DIRECTORY

cd YOUR_DIRECTORY

## docker_yaml Mysql and Adminer:

    environment:
        MYSQL_ROOT_PASSWORD: 'secret'
        MYSQL_PASSWORD: 'secret'
        MYSQL_DATABASE: 'symfony_docker'
        MYSQL_USER: 'symfony'
    
    adminer
    adminer-service:
        image: adminer:latest
        restart: always
        ports:
            - 8080:8080
        environment:
            ADMINER_DEFAULT_SERVER: mysql8-container
        networks:
            - nginx-php74-mysql8-node

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