## Nginx Server Name Virtual Host

**Description**

> Setup simple virtual host config for a server name
>
> Specs:
>
> * Nginx: 1.10
> * Ubuntu 14.04

**Code**

```
# vi /etc/nginx/sites-available/example.com
----------------------------------------------
 server {
        listen   80; ## listen for ipv4; this line is default and implied
        #listen   [::]:80 default ipv6only=on; ## listen for ipv6

        server_name your_server_name.com # comment it to listen on all server name 

        root /var/www/your_server_name.com/public_html;
        index index.html index.htm;

        # Make site accessible from http://localhost/
        server_name example.com;
}
```

**Source**

* [https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-virtual-hosts-server-blocks-on-ubuntu-12-04-lts--3](https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-virtual-hosts-server-blocks-on-ubuntu-12-04-lts--3)

**Extra Information**

**Tags**

\#nginx \#virtualhost \#server-name-based



