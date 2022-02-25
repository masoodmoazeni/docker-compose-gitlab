# Compose file for Gitlab Community Edition

[![License](https://img.shields.io/github/license/mgcrea/docker-compose-gitlab-ce.svg?style=flat)](https://tldrlegal.com/license/mit-license)
[![Docker Stars](https://img.shields.io/docker/stars/gitlab/gitlab-ce.svg)](https://registry.hub.docker.com/u/gitlab/gitlab-ce/)
[![Docker Pulls](https://img.shields.io/docker/pulls/gitlab/gitlab-ce.svg)](https://registry.hub.docker.com/u/gitlab/gitlab-ce/)

Working `docker-compose.yml` for official [gitlab-ce](https://hub.docker.com/r/gitlab/gitlab-ce) docker images leveraging separate instances for services:

- Uses official [postgres](https://hub.docker.com/_/postgres/) docker image
- Uses official [redis](https://hub.docker.com/_/redis/) docker image
- Comes with a [gitlab-runner](https://hub.docker.com/r/gitlab/gitlab-runner/) instance

Made to work behind a separate automated [nginx-proxy](https://github.com/jwilder/nginx-proxy) with SSL support via letsencrypt.

--------


when you create folder for file directory git lab
you can use from these command in linux

```bash
mkdir -p /{config,logs,data}
```

Gitlab installation
Containers are started using the command:

```bash
> docker-compose up -d
````
after 5 or 10 minute config system on linux you can see 
admin gitlab and login

with

```bash
> docker ps
````

when you log in for first time you have to run command for create password and login it
```bash
> docker exec -it gitlab-ce grep 'Password:' /etc/gitlab/initial_root_password

Password: LjuA9pytEZvkN948maZbFHOoXk+o9RbWxQZRETIMp4A=

````

and you see these password , 
you can login with
<br/>
username:root
<br/>
password:LjuA9pytEZvkN948maZbFHOoXk+o9RbWxQZRETIMp4A=

these password create random for you when you install gitlab you run these command and get password for first time.




when you use these url for 

https://www.czerniga.it/2021/11/14/how-to-install-gitlab-using-docker-compose/

