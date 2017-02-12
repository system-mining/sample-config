### Nginx php-fpm configuration

**Description**

> Setup Nginx run with PHP-fpm to process php file via unix socket

**Config**

```
# vi /etc/nginx/site-avaiable/php-fpm.conf

server {
    listen 80 default_server;

    root /usr/share/nginx/example.com;
    index index.php index.html index.htm;

    server_name example.com www.example.com;
    location / {
        try_files $uri $uri/ /index.php;
    }

    location ~ \.php$ {
        try_files $uri =404;
        fastcgi_pass unix:/var/run/php5-fpm.sock;  # find socket file in /etc/php/fpm directory
        fastcgi_index index.php;
        include fastcgi_params;
    }
}

```

**Source: **

* [https://support.rackspace.com/how-to/install-nginx-and-php-fpm-running-on-unix-file-sockets/](https://support.rackspace.com/how-to/install-nginx-and-php-fpm-running-on-unix-file-sockets/)
* [/h ttp://blog.chrismeller.com/configuring-and-optimizing-php-fpm-and-nginx-on-ubuntu-or-debian](/h ttp://blog.chrismeller.com/configuring-and-optimizing-php-fpm-and-nginx-on-ubuntu-or-debian)

**Extra information**



**Tags:**

\#nginx \#php-fpm  \#unix-socket



