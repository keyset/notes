|Command|Notes|
|---|---|
|`docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=P@ssword1" -p 1433:1433 -v c:/data:/var/opt/mssql/data --name mssql2019d -d mcr.microsoft.com/mssql/server:2019-latest`|Run a new SQL Developer edition container called `mssql2019d`, mapping local directory|
|`docker cp C:\Data\SQLServer\. mssql2019d:/var/backups`|Copy local directory to container|
|`docker ps -a`|List all containers including those that are stopped|
|`docker rm mssql2019d`|Delete the container called `mssql2019d`|
|`docker run --name tkeyser-postgres -e POSTGRES_PASSWORD=P@ssword1 -d postgres`|Run a new Postgres container|
|`docker run --link tkeyser-postgres:db -p 8080:8080 adminer`|Run a new adminer container linked to above Postgres container|
