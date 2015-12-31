# Docker container for MySQL

This container works exactly the same as the official Docker MySQL container (https://hub.docker.com/_/mysql/) but with 2 added environment variables (SETUID and SETGID) for setting the user and group IDs.

The main purpose of adding this was so I could set the owner of mounted volume.

### Usage
```
git clone https://github.com/mdusher/docker-mysql
cd docker-mysql
docker build -t mdusher/mysql .
docker run --name mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -v /docker/mysql/data:/var/lib/mysql -e SETUID=1000 -e SETGID=1000 -d mdusher/mysql
```
