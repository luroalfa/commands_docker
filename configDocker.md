# Commands of docker:
Este comando se utiliza para ejecutar una imagen de Microsoft SQL Server 2022 en un contenedor.
```
docker run --name SQLServer -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=YOUR_PASS' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2022-latest
```
Los parámetros utilizados en este comando son:

* **--name SQLServer:** Este parámetro se utiliza para asignar un nombre al contenedor, en este caso "SQLServer".

* **-e 'ACCEPT_EULA=Y':** Este parámetro se utiliza para aceptar los términos de licencia de usuario final de Microsoft. El valor "Y" indica que se aceptan los términos, la cual es una variable de entorno.

* **-e 'MSSQL_SA_PASSWORD=YOUR_PASS':** Este parámetro se utiliza para establecer una contraseña para la cuenta de administrador del servidor. Es importante utilizar una contraseña segura, la cual es una variable de entorno.

* **-p 1433:1433:** Este parámetro se utiliza para exponer el puerto 1433 del contenedor al host. El formato es host_port:container_port

* **-d:** Este parámetro especifica que el contenedor debe ejecutarse en segundo plano.

* **mcr.microsoft.com/mssql/server:2022-latest:** Este es el nombre de la imagen de contenedor de Microsoft SQL Server 2022 más reciente que se utilizará para ejecutar el contenedor.

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

El comando 
```
docker rm $(docker ps -aq) 
```
se usa para eliminar todos los contenedores detenidos.

**$(docker ps -aq)** es una sustitución de comando, ejecutará el comando **docker ps -aq** y sustituirá la salida de ese comando como argumento del comando **docker rm**. El comando **docker ps -aq** enumera todos los ID de contenedor en el sistema, incluidos aquellos que están detenidos o inactivos.
Entonces, este comando eliminará todos los contenedores que están detenidos actualmente, no eliminará los contenedores que se están ejecutando. Este comando es útil cuando desea limpiar contenedores detenidos y liberar espacio en disco. Sin embargo, es importante usar este comando con precaución, ya que eliminará todos los contenedores que no se estén ejecutando actualmente, lo que significa que si tiene datos importantes en esos contenedores, se perderán. Siempre es una buena práctica verificar dos veces la lista de contenedores antes de ejecutar este comando.