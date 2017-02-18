## Mailhog docker-compose yml

**Description:**

> Web and API based SMTP testing for development phase
>
> Specs
>
> * Docker: 1.12
>
> * Docker-compose 1.7.1

**Config**

```
# vi docker-compose.yml
# Add mailhog service into stack

version: '2'
services:
  mailhog:
      image: mailhog/mailhog
      container_name: mailhog
      ports:
       - "1025:1025"
       - "8025:8025"
     environment: 
       - MH_STORAGE=maildir
       - MH_MAILDIR_PATH=/tmp/mailhog
     volumes:
       - ./maildir:/tmp/mailhog
```

**Source:**

* [https://github.com/mailhog/MailHog](https://github.com/mailhog/MailHog)

**Extra infomation:**

**Tags:**

\#mailhog \#docker-compose \#docker

