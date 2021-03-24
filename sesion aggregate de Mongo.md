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

#### 2. Sistema agregacion RangoDB.Pipeline
