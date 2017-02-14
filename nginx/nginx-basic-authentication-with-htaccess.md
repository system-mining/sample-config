## Nginx With Basic Authentication

**Description:**

> `htpasswd`is used to create and update the flat-files used to store usernames and password for basic authentication of HTTP users

**Config**

##### 1. Htpasswd File

```
Config# Generate:
$ sudo htpasswd -c /etc/nginx/.htpasswd sample_user
$ sudo htpasswd /etc/nginx/.htpasswd another_user

$ cat /etc/apache2/.htpasswd
# Output
sample_user:$apr1$lzxsIfXG$tmCvCfb49vpPFwKGVsuYz.
another_user:$apr1$p1E9MeAf$kiAhneUwr.MhAE2kKGYHK.
```

##### 2. Nginx configuration

```
# vi /etc/nginx/sites-available/sample-auth.conf

<server {
    listen 80 default_server;
    listen [::]:80 default_server ipv6only=on;

    root /usr/share/nginx/html;
    index index.html index.htm;

    server_name localhost;

    location / {
        try_files $uri $uri/ =404;
        auth_basic "Restricted Content";
        auth_basic_user_file /etc/nginx/.htpasswd;
    }
}
```

**Source:**

* [https://www.digitalocean.com/community/tutorials/how-to-set-up-password-authentication-with-nginx-on-ubuntu-14-04](https://www.digitalocean.com/community/tutorials/how-to-set-up-password-authentication-with-nginx-on-ubuntu-14-04)
* Htpassword generator online: [http://www.htaccesstools.com/htpasswd-generator/](http://www.htaccesstools.com/htpasswd-generator/)

**Extra information:**

TOBEUPDATE

**Tags:**

\#nginx \#authentication \#http\_authentication \#htpasswd \#htpassword

