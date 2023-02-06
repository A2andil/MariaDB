### Creating a Container from the Latest Version of a Docker Image
```
docker pull mariadb
```
```
docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -p 3306:3306 -d docker.io/library/mariadb
```
