### Apache Virtual Host Directory

**Description:**

**Config:**

```
# vi /usr/local/apache2/sites-available/vhosts.conf
# Directory config with allow override

VirtualHost *:80>
        ServerAdmin webmaster@localhost

        DocumentRoot /var/www/phalcon/web
        <Directory />
                Options FollowSymLinks
                AllowOverride None
        </Directory>
        <Directory /var/www/>
                Options Indexes FollowSymLinks MultiViews
                AllowOverride All
                Order allow,deny
                allow from all
        </Directory>

        ErrorLog /dev/stderr debug

        # Possible values include: debug, info, notice, warn, error, crit,
        # alert, emerg.
        LogLevel debug
</VirtualHost>
```

**Source:**

* [https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-14-04-lts](https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-14-04-lts)
* [https://httpd.apache.org/docs/2.4/vhosts/examples.html](https://httpd.apache.org/docs/2.4/vhosts/examples.html)



