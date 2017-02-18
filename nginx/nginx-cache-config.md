## Nginx Proxy cache config

**Description**

> Simple setup cache for caching  proxy content on Nginx to improve application performance
>
> Specs:
>
> * Ubuntu 16.04
> * Nginx 1.11

**Config**

```shell
proxy_cache_path path/to/cache levels=1:2 keys_zone=my_cache:10m max_size=10g
                 inactive=60m use_temp_path=off

server {
        server_name example.server.com
#       ........     
        location / { 
                add_header X-Cache-Status $upstream_cache_status;
                # Declare cache config
                proxy_cache my_cache;

                # Custom cache key
                proxy_cache_key $host$uri$is_args$args; 
                proxy_cache_valid 200 10m;

                proxy_pass http://your_upstream;

                # Use secret header to by pass cacje
                proxy_cache_bypass $http_secret_header;

        }
```

**Source**

* [https://www.nginx.com/blog/nginx-caching-guide/](https://www.nginx.com/blog/nginx-caching-guide/)
* [https://www.nginx.com/blog/nginx-caching-guide/\#caching-guide-faq-hole-punch](https://www.nginx.com/blog/nginx-caching-guide/#caching-guide-faq-hole-punch)

**Extra information:**

TOBEUPDATE

**Tags:**

\#nginx \#nginx_cache \#proxycache _

