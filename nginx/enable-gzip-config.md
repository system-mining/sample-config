## Enable Gzip Configure

**Description**

> Enable gzip configure on nginx server
>
> Specs:
>
> * Ubuntu: 14.04
> * Nginx 1.4.6

**Config**

    # vi /etc/nginx/nginx.conf
    --------------------------------------------------
    #. . . other config
    ##
    # `gzip` Settings
    #
    #
    gzip on;
    gzip_disable "msie6";

    gzip_vary on;
    gzip_proxied any;
    gzip_comp_level 6;
    gzip_buffers 16 8k;
    gzip_http_version 1.1;
    gzip_min_length 256;
    gzip_types text/plain text/css application/json application/x-javascript text/xml application/xml application/xml+rss text/javascript application/vnd.ms-fontobject application/x-font-ttf font/opentype image/svg+xml image/x-icon;

    #. . . other config

**Source**

* [https://www.digitalocean.com/community/tutorials/how-to-add-the-gzip-module-to-nginx-on-ubuntu-14-04](https://www.digitalocean.com/community/tutorials/how-to-add-the-gzip-module-to-nginx-on-ubuntu-14-04)

**Extra Information**

**Tags**

\#nginx \#gzip



