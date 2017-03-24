## Elasticsearch Kibana docker-compose.yml

**Description**

> Quickstart  elasticsearch kibana application
>
> Specs:
>
> * Docker 1.12
> * Docker-compose 1.8
> * Ubuntu: 16.04
> * Kibana: 5.2

**Config**

```
# vi docker-compose.yml
#----------------------------------------
version: "2"
  elasticsearch:
    image: elasticsearch:5.2
    ports:
      - 9200:9200
      - 9300:9300
    volumes:
      - ./stack/elasticsearch/.esdata:/usr/share/elasticsearch/data:rw
  
  kibana:
    image: docker.elastic.co/kibana/kibana:5.2.1
    links:
      - elasticsearch:elasticsearch
    ports:
      - 5601:5601
```

**Source**

* [https://hub.docker.com/\_/elasticsearch/](https://hub.docker.com/_/elasticsearch/)
* [https://www.elastic.co/guide/en/kibana/current/\_pulling\_the\_image.html](https://www.elastic.co/guide/en/kibana/current/_pulling_the_image.html)

**Extra information**

If your meet vm.max-size error, run command below before run \`docker-compose up\`

```
sudo sysctl vm.max_map_count=262144
```

**Tags**

\#elasticsearch \#kibana \#docker \#docker-compose





