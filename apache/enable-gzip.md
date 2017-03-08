## Enable gzip on apache2

**Description**

> Enable gzip on apache2 for optimize page speed
>
> Specs:
>
> * Ubuntu 14.04
> * Apache 2.4.0
> * mod\_deflate enabled

**Config**

```
# vi /etc/apache2/mods-enabled/deflate.conf
# ---------------------------------------------

<IfModule mod_deflate.c>
        <IfModule mod_filter.c>
                # these are known to be safe with MSIE 6
                AddOutputFilterByType DEFLATE text/html text/plain text/xml

                # everything else may cause problems with MSIE 6
                AddOutputFilterByType DEFLATE text/css
                AddOutputFilterByType DEFLATE application/x-javascript application/javascript application/ecmascript
                AddOutputFilterByType DEFLATE application/rss+xml
                AddOutputFilterByType DEFLATE application/xml
        </IfModule>
</IfModule>
```

**Source**

* [https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-mod\_deflate-on-ubuntu-14-04](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-mod_deflate-on-ubuntu-14-04)

**Extra Information**

**Tags**

\#apache2 \#gzip \#mod\_deflate







