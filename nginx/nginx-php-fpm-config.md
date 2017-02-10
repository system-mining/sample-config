#### Nginx php-fpm configuration



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
        fastcgi_pass unix:/var/run/php5-fpm.sock;
        fastcgi_index index.php;
        include fastcgi_params;
    }
}
```



