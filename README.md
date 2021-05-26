

### Guia de Mongo
By: Ronal Forero
<p align="center"><img src="https://github.com/l337quez/mongo/blob/master/img/og-meta-vnnknnoyi0.png?raw=true"></p>  

<br/>

### Índice 
* [Mongo en Linux](#item1)
* [Restaurar o importar DB](#item2)
* [Exportar salida de una Query MONGO a CSV](#item2.1)
* [Revisar indexacion de la base de datos](#item3)
* [Indexado 2d](#item4)
* [Listar base de datos y colecciones](#item5)
* [Consultas a Mongo con JS](#consultas_con_js)
* [Operadores de Mongo](#operadores)



<br/>

<a name="item1"></a>
### Mongo en Linux
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

<a name="item2"></a>
### Restaurar o importar DB
si usas windows, hay que agregar mongo al path.
No necesitamos entrar a Mongo para hacer estas operaciones
### Exportar base
```
mongodump --db nombre_db -o ruta
```
<br/>

### Importar base de datos
Importante: Para importar la una base de datos debe haber una carpeta llamada "dump" y dentro de esta deben estar todos los archivos, tambien debes conocer el nombre de la base de datos.
<span style="color:red">Si la version de mongo es superio a la version 4, puedes cambiar el nombre de la base de datos, simplemente donde dice nombre_de_base_de_datos pones cualquier nombre</span> 
 <span style="color:red">cardenasddddddddles</span>.

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

<a name="item2.1"></a>
### Exportar salida de una Query MONGO a CSV
Si quieres guardar en un archivo csv la salida de una query, esta es una buena opcion. Yo usualmente hacia un script con la conexion a la base de datos, tambien usaba mongoose para hacer la query, usaba un script para convertir la salida en csv, pero hacer todo esto de una manera simplificada, es copiar un simple comando en la terminal y obtener el resultado en un archivo csv.

<br/>

**nombre_DB =** nombre de la base de datos que vamos a usar  
**nombre_archivo.js =** aqui puedes poner la ruta del archivo js donde esta la query o si estas posicionado en la rutas, podemos poner solo el nombre del archivo.  
**nombre_salida =** es el nombre que va adoptar el archivo de salida generado por Mongo.  

```
mongo nombre_DB nombre_archivo.js > nombre_salida.csv
```

<br/>

Ejemplo: Aqui un ejemplo sencillo de lo que tiene el archivo js. Debe tener la Query, pero esta debe ser en mongo directo. Vamos a suponer que existe una coleccion llamada users
```
db.users.find({name:1})
```

<br/>


<a name="consultas_con_js"></a>
### Hacer consultas a Mongo con JS
Si no deseas usar un interprete como Moongose, entonces puedes hacer tus consultas con JS, es bastante comodo como para cuando necesitas hacer un script o algo para solucionar rapido. Puedes usar print, es como el console.log en Mongo. Lo demas lo puedes hacer con JS...

<br/>

**nombre_DB =** nombre de la base de datos que vamos a usar  
**nombre_archivo.js =** aqui puedes poner la ruta del archivo js donde esta la query o si estas posicionado en la rutas, podemos poner solo el nombre del archivo.  

```
mongo nombre_DB nombre_archivo.js 
```

<br/>

<a name="operadores"></a>
### Operadores de Mongo
Si no deseas usar un interprete como Moongose, entonces puedes hacer tus consultas con JS, es bastante comodo como para cuando necesitas hacer un script o algo para solucionar rapido. Puedes usar print, es como el console.log en Mongo. Lo demas lo puedes hacer con JS...

<br/>

**gte =** Mayor o igual que
```js
{ createdAt:{$gte: new Date("2021-05-25T00:00:00Z") }
```
$eq - equal - igual
$lt - low than - menor que
$lte - low than equal - menor o igual que
$gt - greater than - mayor que
$ne - not equal - distinto
$in - in - dentro de
$nin - not in - no dentro de



<br/>
<br/>

<a name="item3"></a>
### Revisar indexacion de la base de datos
A veces suele ser necesario revisar que tipo de indexado tiene una coleccion, asi que con el siguiente comando lo podremos hacer.
```
db.nombre_coleccion.getIndexes()
```

<br/>

<a name="item4"></a>
### Indexado tipo 2d
Este tipo de indexacion es para geolocaclizacion con altitude y latitude. Para indexar la coleccion debe usar el siguiente comando

```
db.nombre_de_la_coleccion.ensureIndex({"location": "2d"})
```

<br/>

<a name="item5"></a>
### Listar base de datos y colecciones
Entramos a mongo escribiendo mongo en la terminal.

#### Listar base de datos
```
show dbs
```

<br/>

#### Usar una base de datos
```
use dbs
```

<br/>

#### Listar colecciones
para ejecutar este comando debemos previamente haber escogido una base de datos.

```
show collections
```

<br/>


#### Trabajar con fechas en mongo
http://rafinguer.blogspot.com/2014/10/fechas-en-mongodb.html

https://rafinguer.blogspot.com/2014/10/fechas-en-mongodb.html

https://www.ramoncarrasco.es/es/content/es/kb/126/como-hacer-consultas-en-mongodb-operadores
