# 

# Nginx Reverse Proxy Config

### Reverse proxy with subcategory uri

```
server {
    location /checkin/ {
       rewrite ^/checkin(/.*)$ $1 break;
       add_header Access-Control-Allow-Origin *;
       add_header X-Frame-Options SAMEORIGIN;
       proxy_pass http://localhost:8181;
       proxy_http_version 1.1;
       proxy_set_header Upgrade $http_upgrade;
       proxy_set_header Connection 'upgrade';
       proxy_set_header Host $host;
       proxy_cache_bypass $http_upgrade;
   }
}
```



