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

### Create API and Install Package 
```
dotnet new webapi
dotnet add package Pomelo.EntityFrameworkCore.MySql
dotnet build
```

### Appsettings.json connection string
```
"ConnectionStrings": {
    "MariaDbConnectionString": "server=localhost;user id=root;password=root;database=aspnetcore.mariadb"
  }
```

### Weather Model
```
public class WeatherForecastDataModel
{
    public int? Id { get; set; }

    public DateTime Date { get; set; }

    public int TemperatureC { get; set; }

    public int TemperatureF => 32 + (int)(TemperatureC / 0.5556);

    public string Summary { get; set; }
}
```

### DbContext
```
public partial class MariaDbContext : Microsoft.EntityFrameworkCore.DbContext
{
    public MariaDbContext(DbContextOptions<MariaDbContext> options)
        : base(options)
    {
    }

    public virtual DbSet<WeatherForecastDataModel> WeatherForecasts { get; set; }
}
```

### Dependency Injection
```
services.AddDbContextPool<MariaDbDbContext>(options => options
        .UseMySql(
            Configuration.GetConnectionString("MariaDbConnectionString"),
            mySqlOptions => mySqlOptions.ServerVersion(new Version(10, 5, 4), ServerType.MariaDb)
        )
    );
    
```
