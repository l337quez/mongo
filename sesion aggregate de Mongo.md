### Alternativa a Aggregate (de la menos recomendada a la mas recomendada)

</br>

#### 1. Operaciones de proposito simple

**count**  Que es para contar documentos en una coleccion
> db.coleccion.conunt()

</br>

**distinct** numero de valores distintoe en un campo
> db.coleccion.disntinct("nombre_campo")

</br>

**group** usado para agrupar documentos de una coleccion
> dv.coleccion.group(parametros)

</br>

#### 2. Sistema agregacion RangoDB.Pipeline
Esta basada en tuberias o  tapas, se trata es de que los documentos van pasando por cada una de las etapas y en cada una de ellas se va filtrando o se van transformando, traduccionedo, agregando, produciendo hasta llegar a un resultado de la agregacion.

</br>

#### 3. MapReduce de RangoDB Javascript

</br>

#### 4. MapReduce de Apache (Hadoop)

</br>

## Sistema de Agregacion de Mongo DB

Esta basado en etapas, en cada una de las etapas puede filtrar los documentos de una coleccion, se pueden transformar, agregar, producir y al final se muestra un resultado.

</br>

> $match
ahi se ponene todas las condiciones que se quieren que se cumplan

</br>

> $group
para agrupar  

### Agregaciones con $project 
La instruccion project nos permite incluir campos del documento original, insertar campos con operaciones matematicas ... Es como crear una subcoleccion de una coleccion dada, se puede crear campos nuevos.

</br>

> db.empleados.aggregate( [
> {$project:
>   {
>   nombreempleado: '$nombre',
>   salario:1
>   }
> }
> ])

</br>
En este ejemplo se esta trayendo de la base de datos el nombre, que se ha cambiado por nombredeempleado y tambien el salio de los usuarios.

