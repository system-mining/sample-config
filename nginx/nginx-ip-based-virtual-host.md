## Nginx Ip-based virtualhost

**Description**

> Setup **IP-based **virtual hosts for different `IP:port`connection
>
> Specs:
>
> * Ubuntu 14.04
> * Nginx 1.10

**Config:**

```
# vi /etc/nginx/sites-available/ip-based-sample.conf
------------------------------------------------------

# listen on ip-1
server {
    listen 192.168.1.12:80;

    # serve static files
    location / {
        root /var/www/virtual/ip-1;
    }
}

# listen on ip-2
server {
    listen 192.168.0.22:80;
    
    # serve static files
    location / {
        root /var/www/virtual/ip-2;
    }
}


```

**Source**

* [http://www.tecmint.com/nginx-name-based-and-ip-based-virtual-hosts-server-blocks/?utm\_content=buffer15f0d&utm\_medium=social&utm\_source=facebook.com&utm\_campaign=buffer](http://www.tecmint.com/nginx-name-based-and-ip-based-virtual-hosts-server-blocks/?utm_content=buffer15f0d&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer)

**Extra infomation**

**Tags**

\#nginx \#ip-based 

