si usas windows, hay que agregar mongo al path.

### No necesitamos entrar a mongo para hacer estas operaciones

## Exportar base
mongodump --db nombre_db -o ruta

## Importar base de datos
mongorestore --db nombre_base_de_datos ruta_de_la_carpeta_con_la_db


## Importar una coleccion a la base de datos
mongoimport --db nombre_base_de_datos --collection nombre_de_la_coleccion --type json --file ruta_nombrearchivo.json --jsonArray

Nota: Si proporciona un solo documento, no utilice la opción --jsonArray.
