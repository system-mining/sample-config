### Sample Configuration

#### I. Introduction

##### The collection of sample configuration of applications for quick search & use

* Apache
* Nginx
* Docker
* Docker compose
* .... 

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

---

#### Apache Virtual Host Configuration

```
# vi /usr/local/apache2/sites-available/vhosts.conf
NameVirtualHost *:80

<VirtualHost *:80>
    ServerAdmin admin@webmaster.com

    DocumentRoot "/var/www/ex1"
    ServerName example_1.com
    ServerAlias www.example_1.com

    ErrorLog "/var/log/apache2/example_1_error_log"
    CustomLog "/var/log/apache2/example_1_access_log" common
</VirtualHost>

<VirtualHost *:80>
   DocumentRoot "/var/www/ex2"
    ServerName example_2.com
    ServerAlias www.example_2.com

    ErrorLog "/var/log/apache2/example_2_error_log"
    CustomLog "/var/log/apache2/example_2_access_log" common
</VirtualHost>
```

---



