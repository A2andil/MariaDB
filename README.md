### Creating a Container from the Latest Version of a Docker Image:
```
docker pull mariadb
```
```
docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -p 3306:3306 -d docker.io/library/mariadb
```

.Net 6 MySQL Packages
```
- dotnet add package MySql.EntityFrameworkCore --version 6.0.4
- dotnet add package MySql.Data.EntityFrameworkCore --version 8.0.22
- dotnet add package Microsoft.EntityFrameworkCore.Tools
```
