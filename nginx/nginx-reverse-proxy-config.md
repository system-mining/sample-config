### Nginx Reverse Proxy Configuration

**Description:**

>

**Config:**

```
server {

       location /checkin/ {
              rewrite ^/checkin(/.*)$ $1 break;
              
              #Enable CORS
              add_header Access-Control-Allow-Origin *;
              add_header X-Frame-Options SAMEORIGIN;
              
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

**Source:**



**Tags:**

\#nginx \#reverse\_proxy \#cors

