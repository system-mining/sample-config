## Ssh config file

> Description: 
>
>  - You probably log in and out of a lot of remote servers \(or these days, local virtual machines\) on a daily basis. And it hard to remember all of the various usernames, remote addresses and command line options for things like specifying a non-standard connection port or forwarding local ports to the remote machine.
>
> -  The easy way is add it into ~/.ssh/config file

#### Config

```shell
# vi ~/.ssh/config

---------------------------------------------------------------
# Declare alias name for host with host address, port, username
# Now you can access with `ssh server_1`

Host server_1
    HostName server_1.host.example.com
    Port 22000
    User fooey
    
-------------------------------------------------------------    
# Declare alias name for host with host address, port, username & ssh key
# Now you can access with `ssh server_2`

Host server_2
    HostName server_2.host.example.com
    Port 22000
    User fooey
    IdentityFile ~/.ssh/server_2.key


-------------------------------------------------------------    
# Multi github account with different key
# Now you can clone code via address:

project_1: git@github.project_1:company_a/project_1.gitr
project_2: git@github.project_1:company_a/project_1.git

Host github.project_1
    HostName github.com
    Port 22
    User git
    IdentityFile ~/.ssh/gihub.project_1.key

Host github.project_2
    HostName github.com
    Port 22
    User git
    IdentityFile ~/.ssh/gihub.project_2.key

```

#### Source:

* [http://nerderati.com/2011/03/17/simplify-your-life-with-an-ssh-config-file/](http://nerderati.com/2011/03/17/simplify-your-life-with-an-ssh-config-file/)

* [https://www.cyberciti.biz/faq/create-ssh-config-file-on-linux-unix/](https://www.cyberciti.biz/faq/create-ssh-config-file-on-linux-unix/)

#### Tags: 

\#git \#ssh\_config \#.ssh/config \#openssh



