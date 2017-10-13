# Docker Cheatsheet

Redeploying a container
```
docker pull mysql
docker stop my-mysql-container
docker rm my-mysql-container
docker run --name=my-mysql-container --restart=always \
  -e MYSQL_ROOT_PASSWORD=mypwd -v /my/data/dir:/var/lib/mysql -d mysql
  ```
 
View logs for last 500 lines and follow

```docker logs -f --tail=500 <container name>```
