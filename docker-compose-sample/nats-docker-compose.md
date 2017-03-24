## Nats docker-compose yml

**Description:**

> NATS is an open-source, high-performance, cloud native messaging system.
>
> Specs
>
> * Docker: 1.12
>
> * Docker-compose 1.7.1

**Config**

```
# vi docker-compose.yml
# Add nats service into stack

version: '2'
services:
  nats:
      image: nats
      container_name: nats
      ports:
       - 8222:8222
       - 4222:4222
       - 6222:6222
```

**Source:**

* [https://hub.docker.com/\_/nats/](https://hub.docker.com/_/nats/) 

**Extra infomation:**

**Tags:**

\#nats \#docker-compose \#docker

