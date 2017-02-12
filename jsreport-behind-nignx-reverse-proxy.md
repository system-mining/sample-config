## JsReport Behind Nginx Reverse Proxy

**Description:**

> Jsreport behind nginx reverse proxy on ubuntu

**Config:**

```
upstream jsreport {
    # change port 8080 with the port you are running jsreport on
    server 127.0.0.1:8080;
    keepalive 15;
}

server {
    listen 80;

    # change my-domain.net with the host you run nginx on
    server_name my-domain.net;

    location /socket.io/ {
      proxy_pass http://jsreport;
      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection 'upgrade';
        proxy_redirect off;
        proxy_buffers 8 32k;
        proxy_buffer_size 64k;

        proxy_set_header X-Real-IP $remote_addr;
      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header Host $http_host;
        proxy_set_header X-NginX-Proxy true;
    }

    # change /reporting/ with any subpath you like
    location /reporting/ {
        proxy_pass http://127.0.0.1:8080/;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_cache_bypass $http_upgrade;      
    }
}
```

**Source: **

* [https://jsreport.net/blog/jsreport-behind-nginx-on-ubuntu](https://jsreport.net/blog/jsreport-behind-nginx-on-ubuntu)

**Extra information:**

