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

**Source:**

* [https://forums.docker.com/t/how-do-i-change-the-docker-image-installation-directory/1169](https://forums.docker.com/t/how-do-i-change-the-docker-image-installation-directory/1169)

**Extra information**

```
# For centos
# sudo vi /etc/sysconfig/docker,
# Add the -g option in the other_args variable: ex. other_args="-g /var/lib/testdir"
```

**Tags:**

\#docker \#docker\_config





