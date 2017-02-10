##### Virtual Host Config with Override

```
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



