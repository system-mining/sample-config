## Mysql docker-compose

**Description:**

> Run mysql database with mysql
>
> Specs
>
> * Docker: 1.17
>
> * Docker-compose 1.7.1

**Config**

```
# vi docker-compose.yml
# Add mysql service into stack

version: '2'
services:
  mysql:
    image: mysql
    container_name: mysql_databases
    ports:
      - 3306:3306
    environment:
      - MYSQL_ROOT_PASSWORD=gu123451
      - MYSQL_DATABASE=sample_database
    volumes:
      - ./stack/mysql/data/mysql:/var/lib/mysql:rw
      - ./stack/entrypoint:/docker-entrypoint-initdb.d #put sql file into here to init database

```

**Source:**

* [https://hub.docker.com/\_/mysql/](https://hub.docker.com/_/nats/) 

**Extra infomation:**

**Tags:**

\#mysql \#database \#docker-compose \#docker

