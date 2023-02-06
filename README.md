### Pull latest docker image and craete container
```
docker pull mariadb
```
```
docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -p 3306:3306 -d docker.io/library/mariadb
```
