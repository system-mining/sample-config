### Sample Configuration

#### I. Introduction

##### The collection of sample configuration of many applications

* Apache
* Nginx
* Docker
* Docker compose
* .... 

---

#### II. Sample configuration file structure:

> ##### 1 - Config name
>
> ##### 2 - Description \[Optional\]
>
> ##### 3 - Config content
>
> ##### 4- Source \[Optional\]
>
> ##### 5- Extras information \[Optional\]

Example:

### Apache Virtual Host Configuration

#### Name-Based Virtual Host

```
# vi /usr/local/apache2/sites-available/vhosts.conf
NameVirtualHost *:80

<VirtualHost *:80>
    ServerAdmin admin@webmaster.com

    DocumentRoot "/var/www/html"
    ServerName example_1.com
    ServerAlias www.example_1.com

    ErrorLog "/var/log/apache2/example_1_error_log"
    CustomLog "/var/log/apache2/example_1_access_log" common
</VirtualHost>

<VirtualHost *:80>
   DocumentRoot "/var/www/html"
    ServerName example_2.com
    ServerAlias www.example_2.com

    ErrorLog "/var/log/apache2/example_2_error_log"
    CustomLog "/var/log/apache2/example_2_access_log" common
</VirtualHost>
```

---



