# NET-API-RestTodoItems

API REST con lista de tareas , recomendable utilizar post sobre la API`https://localhost:5001/api/TodoItems`

#INSTALACION DOCKER / MAC

Descargar la version más reciente de docker, [click aqui](https://store.docker.com/editions/community/docker-ce-desktop-mac?tab=description).

#DOWNLOAD SQL SERVER
`docker pull mcr.microsoft.com/mssql/server`

**Lanzar Docker Image**
`docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Password123' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-latest`

##Parametros

**-d**
This optional parameter launches the Docker container in daemon mode. This means that it runs in the background and doesn’t need its own Terminal window open. You can omit this parameter to have the container run in its own Terminal window.

**--name sql_server_demo**
Another optional parameter. This parameter allows you to name the container. This can be handy when stopping and starting your container from the Terminal.

**-e 'ACCEPT_EULA=Y'**
The Y shows that you agree with the EULA (End User Licence Agreement). This is required in order to have SQL Server for Linux run on your Mac.

**-e 'SA_PASSWORD=reallyStrongPwd123'**
Required parameter that sets the sa database password.

**-p 1433:1433**
This maps the local port 1433 to port 1433 on the container. This is the default TCP port that SQL Server uses to listen for connections.

**microsoft/mssql-server-linux**
This tells Docker which image to use. If you downloaded a different one, use it instead.

Iniciar docker
`docker start $container-name`

Procesos docker
`docker ps -a`

Check docker conteiner
`docker ps`

#Conectarse con SQL SERVER

Desde la terminal usamos el comando mssql 

`mssql -u sa -p Password123`

Una vez realizada la conexion se debe de recibir el siguiente mensaje

`Connecting to localhost...done

      sql-cli version 0.6.0
      Enter ".help" for usage hints.
      mssql>`

Realizar una verificaciones de estado MSSQL

select @@version

````
Microsoft SQL Server vNext (CTP2.0) - 14.0.500.272 (X64) 
Apr 13 2017 11:44:40 
Copyright (C) 2017 Microsoft Corporation. All rights reserved.
Developer Edition (64-bit) on Linux (Ubuntu 16.04.2 LTS)

1 row(s) returned

Executed in 1 ms
 mssql>`

````
