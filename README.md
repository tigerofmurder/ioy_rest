# IoT-tarea

Alumnos:
  Cueva Flores, Jonathan Brandon
  
  Garcia Diaz, German Flavio
  
  Montesinos Apaza, Sergio


# PASOS A SEGUIR
## Antes de iniciar el docker
Verificar si no esta corriendo mysql en su maquina
```
sudo netstat -nlpt |grep 3306
```
Si hay un proceso en ejecucion detener
```
sudo service mysql stop
```
## Ejecutar nuestro archivo .yml
### Crear red interna
```
docker network create <<nombre de red>>
```
para nuestro caso:
```
docker network create iot-network
```
### Inicializar nuestro docker
```
docker-compose up
```
### Ingresamos a nuestro contenedor o VM
```
docker exec -it <<nombre-asignado-por-docker>> bash
```
En nuestro caso
```
docker exec -it iotsecond_mysql_1 bash
```
### Ingresamos a Mysql
```
mysql -u root -p
```
la contraseña de nuestro mysql la especificamos en nuestro archivo .yml para nuestro caso es "password"
### Ingresando a la base de datos "TimeSeries"
```
use TimeSeries
```
### Creando la tabla en nuestra BD
```
CREATE TABLE thingData ( id INT NOT NULL AUTO_INCREMENT PRIMARY KEY, topic varchar(1024), payload varchar(2048), timestamp varchar(15), deleted binary(1) ) 
```
![Captura realizada el 2021-11-29 10 03 11](https://user-images.githubusercontent.com/20243155/143892008-c0e08842-c796-4340-9b59-249d94832ac5.png)
)


# ERRORES QUE TUVIMOS
Version de node-red

![Captura realizada el 2021-11-29 10 03 11](https://user-images.githubusercontent.com/20243155/143892137-c77995d8-e694-4676-9a95-dfb5cd10fb40.png)
Puertos de red

![Captura realizada el 2021-11-29 10 09 52](https://user-images.githubusercontent.com/20243155/143892704-90262589-2c48-4240-bb17-1238fd7a7b42.png)
Ejecucion local de node-red en el puerto 

![Captura realizada el 2021-11-29 10 11 40](https://user-images.githubusercontent.com/20243155/143892978-0b06dd2b-38f3-4fbd-ac91-0f2b99324b7c.png)


