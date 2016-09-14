Lab 2. Ejemplo de modelado de datos complejo con Power BI
================

Introducción
------------

Bien!, hasta ahora hemos jugado con modelos de datos sencillos en Power BI. En estos ejemplos hemos trabajado siempre con un único conjunto de datos (*tabla*). En el mundo real, normalmente tenemos que trabajar con modelos de datos que habitualmente están compuestos por diversas tablas relacionadas entre si (*modelo relacional*)

En este ejemplo, vamos a partir de un proyecto de Power Bi con un modelo de datos previamente cargados. En la primera parte, introduciremos el concepto de **relaciones** y veremos como se trabaja y que implicaciones tiene. En la segunda parte, introduciremos el concepto de **Medida** y veremos las diferencias con las columnas calculadas.


Explorando el modelo de datos actual.
------------

1. Pasar a la vista de **datos** y explorar las diferentes tablas del modelo.
2. Observar el numero de filas de cada tabla. ¿Te impresiona?

3. Pasa ahora a la vista de **Relaciones**. Presta atención a la explicación del instructor!
4. Abre el gestor de relaciones en **Administrar Relaciones**
5. Crea una nueva relación que relacione el campo Fecha de la tabla Ventas con el campo Fecha de la tabla de Fechas. Asegurate de que la relación sea *1 a muchas* y la dirección de filtrado sea *bi-direccional*.
