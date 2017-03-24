## Gitbook docker-compose.yml

**Description**

> Quickstart gitbook with docker-compose
>
> Specs:
>
> * Docker 1.12
> * Docker-compose 1.8

**Config**

```
# vi docker-compose.yml
#----------------------------------------
version: '2' 
services: 
  gitbook:
    image: billryan/gitbook
    ports:
      - "4000:4000"
    volumes:
      - "you_gitbook_directory:/gitbook"
    command: ["gitbook", "serve"]
```

**Source**

* [http://blog.system-mining.xyz/from-create-to-deploy-a-gitbook-document-with-gitbook-editor-and-docker/](http://blog.system-mining.xyz/from-create-to-deploy-a-gitbook-document-with-gitbook-editor-and-docker/)
* [https://github.com/GitbookIO/gitbook](https://github.com/GitbookIO/gitbook)

**Extra information**

Simple makefile to working with gitbook

```
# vi Makefile

# Gitbook build command
gitbook-build:
        docker run --rm -v $$(pwd):/gitbook billryan/gitbook gitbook build

# Gitbook install command
gitbook-install:
        docker run --rm -v $$(pwd):/gitbook billryan/gitbook gitbook install

# Gitbook install command
gitbook-serve: 
        docker run --rm -v $$(pwd):/gitbook billryan/gitbook gitbook serve 
```

**Tags**

\#docker \#docker-compose \#makefile \#gitbook \#git



