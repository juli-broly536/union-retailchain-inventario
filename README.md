## Filas devueltas por cada consulta
**¿Cuántas filas devuelve cada consulta y por qué son distintas? Explicá con ejemplos concretos de los datos qué filas se eliminaron con UNION.**

Cada consulta devuelve diferente cantidad de filas, en la consulta 1 nos devuelve 11 filas, la consulta 2 nos devuelve 14 filas, nos da diferente cantidad ya que en la consulta 1 usamos el comando UNION que nos sirve para eliminar los datos duplicados, a diferencia de la consulta 2 que usamos el comando UNION ALL el cual nos trae todos los datos por más que estén repetidos, por ejemplo en la consulta 1 se eliminaron los datos repetidos que son id:103 Monitor 4K 27", id:104 Teclado Mecánico y id:106 SSD Externo 1TB.

## Eficiencia de UNION ALL vs UNION
**¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?**

El UNION ALL puede considerarse más eficiente al usarse ya que solo su trabajo es el de traer todos los datos de las 2 o más consultas que se efectuaron sin tener que buscar si hay datos que se repiten o no. En cambio el comando UNION utiliza internamente más recursos ya que al igual que UNION ALL tiene que hacer un llamado a todas las filas pero antes de mostrarlo tiene que hacer un trabajo extra de comparar todas las filas para buscar filas repetidas, básicamente que sean idénticas entre sí para poder eliminar y dejar solo las filas únicas sin su fila repetida.

## Casos de uso en negocio
**¿En qué casos de negocio usarías cada uno? Dá al menos dos ejemplos reales distintos a los del ejercicio.**

En un caso de negocio el cual tenga 2 maneras de ingreso a mi negocio digital que sean mediante una app o página web, podría tener 2 tablas en mi base de datos que sean los registros en la página web y otra tabla que sean los registros en mi app, si yo quisiera saber solo la cantidad total de clientes que ingresaron a ver mi negocio en cuanto en la página web o en la app, utilizaría el comando UNION para no mostrar datos de clientes que ingresaron más de una vez, a diferencia de que yo quiera hacer un análisis de la cantidad total de ingresos que tuve de cada cliente utilizaría en ese caso UNION ALL.

## Columnas que no coinciden
**¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?**

En el caso que al unir 2 tablas no se coloquen la misma cantidad de columnas, no se va a ejecutar la consulta y va a saltar un error que dice asi: "All queries combined using a UNION, INTERSECT or EXCEPT operator must have an equal number of expressions in their target lists." que basicamente dice que para utilizar el comando UNION entre 2 consultas, las 2 tablas deben estar en iguales condiciones en cuanto cantidad de columnas. En el caso que se muestren la misma cantidad de columnas en las 2 tablas que se hicieron las consultas, pero el tipo de dato es diferente, SQL server intentaria transformarlos primero si los datos son compatibles como un decimal e int, pero en el caso que sean datos incompatibles por ejemplo int y cadena de texto, directamente daria error.
