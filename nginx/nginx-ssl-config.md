## Nginx SSL Config

**Description:**

> Setup SSL to secure the connection between server and client
>
> Specs:
>
> * Ubuntu 16.04
>
> * Nginx 1.11

**Config**

```
# vi /etc/nginx/sites-avaiable/sample-ssl.conf

server {
        listen 80 default_server;
        listen [::]:80 default_server ipv6only=on;

        # Listen on port 443
        listen 443 ssl;

        root /usr/share/nginx/html;
        index index.html index.htm;

        server_name your_domain.com;

        # Config ssl certificate             
        ssl_certificate /etc/nginx/ssl/nginx.crt; # path to your crt file
        ssl_certificate_key /etc/nginx/ssl/nginx.key; # path to your key file

        location / {
                try_files $uri $uri/ =404;
        }
}
```

**Source**

* [https://www.digitalocean.com/community/tutorials/how-to-create-an-ssl-certificate-on-nginx-for-ubuntu-14-04](https://www.digitalocean.com/community/tutorials/how-to-create-an-ssl-certificate-on-nginx-for-ubuntu-14-04)
* [https://www.digicert.com/ssl-certificate-installation-nginx.htm](https://www.digicert.com/ssl-certificate-installation-nginx.htm)
* [http://nginx.org/en/docs/http/configuring\_https\_servers.html](http://nginx.org/en/docs/http/configuring_https_servers.html)

**Extra Information:**

* **Concatenate the primary certificate and intermediate certificate.**

\_You need to concatenate the certificate and your primary key to create the certificate\_

```
cat your_domain_name.crt yourCA.crt >> bundle.crt
```

TOBEUPDATE

**Tags:**

\#nginx \#ssl \#tls

