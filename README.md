### Pull latest docker image and create container
```
docker pull mariadb
```
```
docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -p 3306:3306 -d docker.io/library/mariadb
```
