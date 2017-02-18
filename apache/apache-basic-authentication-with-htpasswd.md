## Apache Virtual Host With Basic Authentication

**Description:**

> `htpasswd`is used to create and update the flat-files used to store usernames and password for basic authentication of HTTP users
>
> Specs:
>
> * Ubuntu 16.04
>
> * Apache 2.4
>
> * Php 5.6

**Config**

##### 1. Htpasswd File

```
Config# Generate:
$ sudo htpasswd -c /etc/apache2/.htpasswd sample_user
$ sudo htpasswd /etc/apache2/.htpasswd another_user

$ cat /etc/apache2/.htpasswd
# Output
sample_user:$apr1$lzxsIfXG$tmCvCfb49vpPFwKGVsuYz.
another_user:$apr1$p1E9MeAf$kiAhneUwr.MhAE2kKGYHK.
```

##### 2. Apache virtual host configuration

```
# vi /etc/apache2/sites-available/sample-auth.conf

<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

    <Directory "/var/www/html">
        AuthType Basic
        AuthName "Restricted Content"
        AuthUserFile /etc/apache2/.htpasswd
        Require valid-user
    </Directory>
</VirtualHost>
```

**Source:**

* [https://httpd.apache.org/docs/current/programs/htpasswd.html](https://httpd.apache.org/docs/current/programs/htpasswd.html)
* Htpassword generator online: [http://www.htaccesstools.com/htpasswd-generator/](http://www.htaccesstools.com/htpasswd-generator/)

**Extra information:**

TOBEUPDATE

**Tags:**

\#apache \#authentication \#http\_authentication \#htpasswd \#htpassword

