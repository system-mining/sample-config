## Apache Virtual Host With Basic Authentication

### 1. Htpasswd File

```
# Generate:
$ sudo htpasswd -c /etc/apache2/.htpasswd sample_user
$ sudo htpasswd /etc/apache2/.htpasswd another_user

$ cat /etc/apache2/.htpasswd
# Output
sample_user:$apr1$lzxsIfXG$tmCvCfb49vpPFwKGVsuYz.
another_user:$apr1$p1E9MeAf$kiAhneUwr.MhAE2kKGYHK.
```

### 2. Apache virtual host configuration

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



