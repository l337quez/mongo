https://ronaldl337.wordpress.com/2020/06/03/tutorial-de-mongo-db-1/


https://1.gravatar.com/avatar/d99438853161ed06e5837632a13204fc?s=400&d=mm


#### Obtener ayudar sobre los comandos de mongo usamos
```sh
db.help()
```

#### Limpiar la consola
```sh
cls
```

#### Para ver todas las bases de datos
```sh
show dbs
```


#### Para crear una base de datos
```sh
use nombre_base_de_datos
```

#### Para crear una coleccion
La base datos de mongo estan conformadas por coleciones, vamos a crear una coleccion e ingresaremos un dato dentro. La coleccion llevara como nombre “Products”. y agregamos a dentro un documento que contenga un espacio llamado name y un valo llamado phone
```sh
db.products.insert({"name":"phone"})
```
Si no desemos agregar nada dentro de la coleccion y simplemente crear la coleccion.

```sh
db.createCollection("products")
```

#### Ver las colecciones dentro de una base de datos


```sh
show collections
```


#### Eliminar una base de datos
```sh
db.dropDatabase()
```

#### Eliminar una coleccion
```sh
db.nombre_collection.drop()
```
