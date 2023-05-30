# Compose file for Gitlab Community Edition

install gitlab and gitlab runner with docker-compose
--
first clone this repository and run

```
docker-compose up -d
```
after that 5 until 10 minute you see gitlab login

after you must run this command for get password 

```
docker exec -it gitlab-ce grep 'Password:' /etc/gitlab/initial_root_password
```
user : root

password : generated

you must change password after that login

tips:please Sign-up enabled ist disable

for register gitlab

first run this command

```
docker exec -it gitlab-runner gitlab-runner register --url "http://gitlab-ce" --clone-url "http://gitlab-ce"
```

--Enter the GitLab instance URL: address website
- Enter the registration token: get token from this address your-address/admin/runner
- Enter a description for the runner : gitlab-runner
- Enter tags for the runner: blank
- Enter an executor: docker
- Enter the default Docker image : httpd
- 

Working `docker-compose.yml` for official [gitlab-ce](https://hub.docker.com/r/gitlab/gitlab-ce) docker images leveraging separate instances for services:

- Uses official [postgres](https://hub.docker.com/_/postgres/) docker image
- Uses official [redis](https://hub.docker.com/_/redis/) docker image
- Comes with a [gitlab-runner](https://hub.docker.com/r/gitlab/gitlab-runner/) instance

Made to work behind a separate automated [nginx-proxy](https://github.com/jwilder/nginx-proxy) with SSL support via letsencrypt.


GitLab Runner
--
if you wanr run gitlab runner on server you must run this command
```
docker-compose exec gitlab-runner gitlab-runner register
```

after that you must answer question for configuration gitlab runner

in your gitlab you must get registry address and registration token
on this address http://your-ip/root/name-project/-/settings/ci_cd

on part runner you can get on it

if you want install gitlab runner on ubuntu you can run these command

```
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash
sudo apt-get install gitlab-runner
apt-cache madison gitlab-runner
gitlab-runner -version
gitlab-runner status
gitlab-runner register
```

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

