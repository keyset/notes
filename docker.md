`docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=P@ssword1" -p 1433:1433 --name mssql2017 -d microsoft/mssql-server-linux:2017-latest`
`docker cp C:\Data\SQLServer\. mssql2017d:/var/backups`

```
USE [master]
RESTORE DATABASE [WideWorldImporters] FROM  DISK = N'/var/backups/WideWorldImporters-Full.bak'
WITH  FILE = 1, NOUNLOAD,  STATS = 5,
MOVE N'WWI_Primary' TO N'/var/opt/mssql/data/WWI/WideWorldImporters.mdf',
MOVE N'WWI_UserData' TO N'/var/opt/mssql/data/WWI/WideWorldImporters_UserData.ndf',
MOVE N'WWI_Log' TO N'/var/opt/mssql/data/WWI/WideWorldImporters.ldf',
MOVE N'WWI_InMemory_Data_1' TO N'/var/opt/mssql/data/WWI/WideWorldImporters_InMemory_Data_1'

RESTORE DATABASE [WideWorldImportersDW] FROM  DISK = N'/var/backups/WideWorldImportersDW-Full.bak'
WITH  FILE = 1, NOUNLOAD,  STATS = 5,
MOVE N'WWI_Primary' TO N'/var/opt/mssql/data/WWI_DW/WideWorldImportersDW.mdf',
MOVE N'WWI_UserData' TO N'/var/opt/mssql/data/WWI_DW/WideWorldImportersDW_UserData.ndf',
MOVE N'WWI_Log' TO N'/var/opt/mssql/data/WWI_DW/WideWorldImportersDW.ldf',
MOVE N'WWIDW_InMemory_Data_1' TO N'/var/opt/mssql/data/WWI_DW/WideWorldImportersDW_InMemory_Data_1'
GO
```
