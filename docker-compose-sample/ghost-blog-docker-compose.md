## Ghost Blog docker compose

**Description**

> Fully open source, hackable platform for building and running a modern online publication
>
> Specs:
>
> * docker: 1.17
> * docker-compose: 1.7

**Config**

```
# vi docker-compose.yml
#----------------------------------------

version: '2'
services:
  ghost:
    image: ghost
    volumes:
      - ./stack/ghost:/var/lib/ghost
    ports:
      - 8080:2368

```

**Source:**

* [https://hub.docker.com/\_/ghost/](https://hub.docker.com/_/ghost/)

**Extra Information**

> * This configure run with build in sqlite database and limited configure of ghost
> * Refer to use build & run with source code & external database for HA & customize

**Tags**

\#blog \#ghost \#docker \#docker-compose



