## Simple Exporter of NFS server

**Description:**

> Simple NFS exporter
>
> Specs:
>
> * Ubuntu 16.04

**Config**

```
# Create Share directory
# sudo mkdir /var/nfs/general -p     
# sudo chown nobody:nogroup /var/nfs/general

# Config
# sudo vi /etc/exports
-----------------------------------
# directory_to_share    client(share_option1,...,share_optionN)

/var/nfs/general    203.0.113.256(rw,sync,no_subtree_check)
```

**Source**

* [https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-ubuntu-16-04](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-ubuntu-16-04)

**Extra information**

**Tags**

\#nfs \#linux





