

### MONGO EN GNU-LInux

#### Activar el servicio de Mongo en GNU Linux
```
sudo systemctl start mongodb.service
```
<br/>

#### Reiniciar el servicio de Mongo
```
sudo systemctl stop mongodb.service
```
<br/>

#### Habilitar el servicio de Mongo para siempre
```
sudo systemctl enable mongodb.service
```
<br/>

#### Entrar a la terminal de mongo
```
mongo
```
<br/>
<br/>
<br/>

============================================================================

si usas windows, hay que agregar mongo al path.
No necesitamos entrar a mongo para hacer estas operaciones
### Exportar base
```
mongodump --db nombre_db -o ruta
```
<br/>

### Importar base de datos
Importante: Para importar la una base de datos debe haber una carpeta llamada "dump" y dentro de esta deben estar todos los archivos, tambien debes conocer el nombre de la base de datos.

```
mongorestore --db nombre_base_de_datos ruta_de_la_carpeta_con_la_db
```
sino funciona intenta esto, dependiendo de la version hay comandos de que no funcionan y a partir cierta version ningnun comando funcionara y
la funcionalidad pasara a un software llamado mongo-tools
```
mongorestore -d db_name /path/
```

<br/>

### Importar una coleccion a la base de datos

```
mongoimport --db nombre_base_de_datos --collection nombre_de_la_coleccion --type json --file ruta_nombrearchivo.json --jsonArray
```

Nota: Si proporciona un solo documento, no utilice la opción --jsonArray.

<br/>
<br/>
<br/>

============================================================================
#### Trabajar con fechas en mongo
http://rafinguer.blogspot.com/2014/10/fechas-en-mongodb.html
