## Wordpress docker-compose.yml 

**Description**

> Quickstart wordpress with docker-compose
>
> Specs:
>
> * Docker 1.12
> * Docker-compose 1.8

**Config**

```
# vi docker-compose.yml
version: '2'

services:
   db:
     image: mysql:5.7
     volumes:
       - db_data:/var/lib/mysql
     restart: always
     environment:
       MYSQL_ROOT_PASSWORD: wordpress
       MYSQL_DATABASE: wordpress
       MYSQL_USER: wordpress
       MYSQL_PASSWORD: wordpress

   wordpress:
     depends_on:
       - db
     image: wordpress:latest
     ports:
       - "8000:80"
     restart: always
     environment:
       WORDPRESS_DB_HOST: db:3306
       WORDPRESS_DB_PASSWORD: wordpress
volumes:
    db_data:
```

**Source**

* [https://docs.docker.com/compose/wordpress/](https://docs.docker.com/compose/wordpress/)

**Extra Information**

ToBeUpdate

**Tags:**

\#docker \#docker-compose \#wordpress



