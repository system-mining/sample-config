## Scrapy splash plugin docker-compose

**Description:**

> [Scrapy](https://github.com/scrapy/scrapy) and JavaScript integration using [Splash](https://github.com/scrapinghub/splash)
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
    image: scrapinghub/splash
    container_name: scrapy-splash
    ports:
      - 5023:5023 
      - 8050:8050 
      - 8051:8051
```

**Source:**

* [https://github.com/scrapy-plugins/scrapy-splash](https://github.com/scrapy-plugins/scrapy-splash)
* [http://splash.readthedocs.io/en/latest/install.html](http://splash.readthedocs.io/en/latest/install.html)

**Extra infomation:**

**Tags:**

\#scrapy \#crawler \#splash \#docker-compose \#docker

