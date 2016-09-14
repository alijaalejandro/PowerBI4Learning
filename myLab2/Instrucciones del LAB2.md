Lab 2. Ejemplo de modelado de datos complejo con Power BI
================

Introducción
------------

Bien!, hasta ahora hemos jugado con modelos de datos sencillos en Power BI. En estos ejemplos hemos trabajado siempre con un único conjunto de datos (*tabla*). En el mundo real, normalmente tenemos que trabajar con modelos de datos que habitualmente están compuestos por diversas tablas relacionadas entre si (*modelo relacional*)

En este ejemplo, vamos a extraer los datos de incidencias de un sistema CRM. En la primera parte, introduciremos el concepto de **relaciones** y veremos como se trabaja y que implicaciones tiene. En la segunda parte, introduciremos el concepto de **Medida** y veremos las diferencias con las columnas calculadas.


Explorando el modelo de datos actual.
------------
*Nota: esta primera parte de conexión con el CRM y extracción de datos la hace solamente el instructor*

1. Descargar y guardar el fichero de Excel en la carpeta de trabajo.
2. **Obtener Datos** -> **Excel** -> **Editar**
3. Eliminar las dos primeras columnas. Puedes selecionar las columnas a la vez haciendo click en una y a continuación en otra manteniedo la tecla **Shift** pulsada.
4. Renombramos la columna *(No modificar) Fecha de modificación* por *Fecha Modificación*
5. Eliminamos la columna Región.
6. Formateamos las columnas con fechas a tipo **Fecha**
7. Renombramos la tabla o conjunto de datos como **Incidencias**
8. Aplicamos y Cerramos.

Relaciones
------------

1. Pasa a la vista de **Datos** y haz click en **Especificar Datos**
2. Crea la siguiente tabla:

![indicador semafórico](indicador_semaforico.PNG)

Aquí teneís los links para copiar:

- Alta --> http://www.fordesigner.com/imguploads/Image/cjbc/zcool/png20080526/1211811447.png
- Normal --> http://www.fordesigner.com/imguploads/Image/cjbc/zcool/png20080526/1211811481.png
- Baja --> http://www.fordesigner.com/imguploads/Image/cjbc/zcool/png20080526/1211811461.png
- 


1. Pasa ahora a la vista de **Relaciones**. Presta atención a la explicación del instructor!
2. Abre el gestor de relaciones en **Administrar Relaciones**
3. Crea una nueva relación que relacione el campo Fecha de la tabla Ventas con el campo Fecha de la tabla de Fechas. Asegurate de que la relación sea *1 a muchas* y la dirección de filtrado sea *bi-direccional*.
