# Commands of docker:
Este comando se utiliza para ejecutar una imagen de Microsoft SQL Server 2022 en un contenedor.
```
docker run --name SQLServer -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=YOUR_PASS' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2022-latest
```
El siguiente comando se utiliza para iniciar un contenedor detenido.
```
docker start <container-name>
```
El siguiente comando se utiliza para deteder un contenedor.
```
docker stop <container-name>
```
El comando 
```
docker ps -aq 
```
Se utiliza para listar todos los contenedores en su sistema, incluidos los que están detenidos o inactivos.
La opción -a indica que se deben mostrar todos los contenedores, incluso los que están detenidos o inactivos.
La opción -q indica que solo se deben mostrar los identificadores únicos (o "IDs") de los contenedores en lugar de mostrar toda la información del contenedor.
El comando docker ps -aq es útil cuando se desea ver una lista rápida de todos los contenedores en el sistema y no se necesita ver toda la información detallada sobre cada contenedor.

El comando
```
docker logs <container_id>
```
Se utiliza para ver los registros de un contenedor específico.
Los registros pueden incluir información sobre la inicialización del contenedor, mensajes de error, registros de depuración y cualquier otra información generada por la aplicación o el servicio que se ejecuta en el contenedor. Los registros son útiles para solucionar problemas y depurar problemas con un contenedor específico.