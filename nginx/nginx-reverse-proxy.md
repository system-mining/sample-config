## Nginx Reverse Proxy

**Decription**

Setup reverse proxy to  distribute the load among several servers, seamlessly show content from different websites, or pass requests for processing to application servers over protocols other than HTTP.

> Specs:
>
> * Ubuntu 16.04
>
> * Nginx 1.11

**Config:**

```
# vi /etc/nginx/sites-available/sample-proxy.conf
server {

       location / {
              proxy_pass http://localhost:8181;

              # Additional Config
              proxy_http_version 1.1;
              proxy_set_header Upgrade $http_upgrade;
              proxy_set_header Connection 'upgrade';
              proxy_set_header Host $host;
              proxy_cache_bypass $http_upgrade;
          }
}
```



