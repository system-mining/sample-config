## Nginx Basic Authentication With Htaccess



### 1. Htpasswd File {#1-htpasswd-file}

```
# Generate:
$ sudo htpasswd -c /etc/nginx/.htpasswd sample_user
$ sudo htpasswd /etc/nginx/.htpasswd another_user

$ cat /etc/nginx/.htpasswd
# Output
sample_user:$apr1$lzxsIfXG$tmCvCfb49vpPFwKGVsuYz.
another_user:$apr1$p1E9MeAf$kiAhneUwr.MhAE2kKGYHK.
```



#### 2. Nginx  Configuration File

```
$ cat /etc/nginx/sites-available/example.conf
# Output
server {
    listen       80;
    server_name  example.com
    location / {
        proxy_pass http://localhost:888;
        auth_basic "Restricted Content";
        auth_basic_user_file /etc/nginx/conf.d/htpasswd;
    }

```



