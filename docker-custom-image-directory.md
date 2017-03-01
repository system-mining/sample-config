## Docker Custom Image Directory

**Description**

> Change image installation directory
>
> Specs:
>
> * Ubuntu 16.04
> * Docker 1.12

**Configure**

```
#sudo vi /etc/default/docker

DOCKER_OPTS="-dns 8.8.8.8 -dns 8.8.4.4 -g /your_custom_dir
```



