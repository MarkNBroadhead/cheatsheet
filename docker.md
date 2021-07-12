# Docker Cheatsheet

## Deploying
### Redeploying a container
```
docker pull mysql
docker stop my-mysql-container
docker rm my-mysql-container
docker run --name=my-mysql-container --restart=always \
  -e MYSQL_ROOT_PASSWORD=mypwd -v /my/data/dir:/var/lib/mysql -d mysql
  ```

### Networking
Connect to host `http://host.docker.internal`

### Troubleshooting
View logs for last 500 lines and follow
```docker logs -f --tail=500 <container name>```

SSH into container 
```docker exec -it <container name> /bin/bash```

Bring up docker image that will remove its self upon exiting shell
```docker run --rm -it ubuntu:16.04 bash -l```

## Cleaning up after docker 
Found this info in a great [blog post](https://getintodevops.com/blog/keeping-the-whale-happy-how-to-clean-up-after-docker)
### Assess the situation
* `df -h`
* `docker ps`
* `docker images`
### Generally safe cleanup commands
* `docker volume rm $(docker volume ls -qf dangling=true)` delete orphaned and dangling volumes
* `docker rmi $(docker images -q -f dangling=true)` delete dangling and untagged images
### Cleanup commands
* `docker rm $(docker ps -aqf status=exited)` delete exited containers
* `docker rmi $(docker images -q)` delete *all* images
* `docker kill $(docker ps -q)` kill *all* running containers
* `docker rm $(docker ps -aq)` delete *all* running containers
### Official Docker cleanup method
* `docker system prune -a`
### Can't run a command?
* `sudo usermod -aG docker $USER`
### Set up a cronjob!
Run this script in a cron job
```
#!/bin/bash
docker rmi $(docker images -q -f dangling=true)
docker volume rm $(docker volume ls -qf dangling=true)
```
cron job: 
`15 0 * * 1 ~/docker-cleanup.sh > /dev/null 2>&1`
