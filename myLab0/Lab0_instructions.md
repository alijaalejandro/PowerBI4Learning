Lab 0. Ejemplo de Solución Extremo a Extremo con Power BI
================

Introducción
------------

En este laboratorio de introducción vamos a ejemplificar un **flujo de datos completo en Power BI**. Desde la **carga original de un conjunto de datos** en formato *CSV* hasta la **creación de un cuadro de mando** personalizado en Power BI service.

Instrucciones
-------------

**IMPORTANTE!** Antes de emprezar.

1.  Ejecute la aplicación Power BI Desktop. *Recuerde que si no lo ha hecho aun puede descargar Power BI gratuitamente en <https://www.microsoft.com/es-ES/download/confirmation.aspx?id=45331>*
2.  Hacer una cuenta gratuita de Power BI en https://powerbi.microsoft.com/es-es/get-started/ 

3.  Actualiar la configuración regional. *Recordar que esta opción se encuentra en el menú de Opciones*
*La configuración regional le indica a Power BI que juego de caracteres y sistema de moneda, fechas, etc ha de utilizar para auto-reconocer los datos que se le proveen*

Introducción a Datos en ficheros de Texto
-------------

1.  Localizar el archivo comprimido *myRENT\_1k.zip* en el directorio de correspondiente al Lab0 de este curso. Si tiene problemas para localizar este directorio recuerde que puede encontrarlo a través del siguiente enlace de descarga directo <https://github.com/alijaalejandro/PowerBI4Learning/raw/master/myLab0/myRENT_1k.zip>.

*Sugerencia*: es buena idea que empieces por crear una carpeta en tus documentos para que puedas ir guardando la información de este curso.

2. Una vez descargado el archivo, prueba a abrirlo con el explorador de Windows. Una vez que accedas a su interior verás el archivo myRENT_1k.csv. Ahora debes de copiar este archivo a la carpeta que has creado anteriormente.

3. A continuación vamos a aprender a importar este tipo de archivos en MS Excel. **Ejecutamos MS Excel y abrimos un libro en blanco**.
4. Ir a **Datos** -> **Obtener Datos Externos** -> **Desde un fichero de Texto**
5. Importa el archivo sabiendo que el delimitador de campos es ";" y el caracter decimal es ","


6.  Si todo ha ido bien deberías de ver algo similar a esto en la hoja de Excel.

<!-- -->

    ##             Empresa      Actividad.Económica Cliente
    ## 1 HUNE RENTAL, S.L. INSTALACIONES ELÉCTRICAS    1008
    ## 2 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119
    ## 3 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119
    ## 4 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119
    ## 5 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119
    ## 6 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119

7. Ahora vamos a aprender a guardar este archivo como tipo MS Excel y como tipo CSV nuevamente.

Introducción a Power BI. Importando datos en formato CSV.
-------------
1. Ejecutamos Power BI Desktop.
2. Vamos a **Obtener Datos** -> **CSV** --> **Editar**

*A continuación se abrirá una nueva pantalla denominada el Query Editor. Este módulo es el encargado de permitir el modelado avanzado de datos con Power BI. Con este módulo podrémos realizar transformaciones a los datos, agregaciones, adaptaciones de formato, etc.*

Detengámonos un momento a observar las diferentes partes de este módulo. Volveremos con más detalle sobre este módulo en el capítulo 3 sobre modelado avanzado de datos con Power BI.

3.  Apliquemos algunas transformaciones básicas.
4.  Hacer Click en **Transformar** -> **Contar Filas**. A continuación elimina este paso en el editor de **Pasos Aplicados**

-   **Pregunta 1**. ¿Cuantas filas tiene este conjunto de datos?
-   **Pregunta 2**. Como puedes observar, Power BI ha identificado automaticamente el tipo de datos que contienen las columnas del conjunto de datos (*Inferencia automática del Esquema*) ¿Ha sido correcta esta asignación?


Primeras Visualizaciones con Power BI
-------------

1.  Hacer click en **Inicio** -> **Aplicar y Cerrar**

2.  Observamos la vista de Power BI Desktop. Disponemos de 3 modos de visualización: **Report**, **Data** y **Relationships**.

3.  Pasamos a modo **Report** Renombramos el Report **MyRent Report**.

4.  Hacemos un **Gráfico de Barras Horizontales** con los campos **Importe** *vs* **Delegación*. Ordenamos por **Importe**
5.  Pasamos a modo **Data** y formateamos adecuadamente. 


6.  A continuación hacemos un **Gráfico de Mapa** con los campos **Importe** y **Delegación**.

Observa el resultado. ¿Qué ha ocurrido? ¿Están correctamente situadas todas las delegaciones?

*Explicación*: power BI tiene cierta inteligencia para detectar datos geográficos, como continentes, paises, ciudades, códigos postales, etc. Sin embargo, como sabéis, los nombres de ciudades no son únicos alrrededor del mundo. Lo ideal es trabajar con indentificadores únicos como códigos postales dentro de un pais o latitud y longitud en todo el mundo. Lo que ocurre es que, en el mundo real, a verces no disponemos de toda la información en perfecto estado. Por eso debemos de aplicar algunos **trucos** para obtener el resultado más próximo a lo que buscamos.
Más info aquí: https://powerbi.microsoft.com/en-us/documentation/powerbi-service-tips-and-tricks-for-power-bi-map-visualizations/


Primeras transformaciones con Power BI
-------------

1.  Volvamos a la vista **Data** y creemos una nueva columna llamada **Pais**. Fijemos el valor de Pais a la constante *España*. Categoricemos esta nueva variable como tipo **Pais**. Para crear una nueva columna, vamos a **Modelado** -> **Nueva Columna** y escribimos la siguiente fórmula:
`Country = "Spain"`

2.  Renombremos la columna **Delegación** como **Ciudad**. Categoricemos como **Ciudad**
3.  Creemos una nueva coluna de nuevo, llamada **Ciudad-Pais**. Para ello escribimos la siguiente fórmula en la barra de creación de una nueva columna:
`Ciudad-Pais = 'My Rent Report'[Ciudad] & "," & 'My Rent Report'[Pais]`

4.  Categoricemos nuevamente la columna **Ciudad-Pais** como tipo Ciudad.

5.  Volvamos a la vista **Report**

6.  Hagamos de nuevo el Map Plot en este caso utilizando la nueva variable **Ciudad-Pais**. Casi lo hemos logrado! solamente ASTURIAS está mal ubicada en el Mapa. Lógico, Asturias no es una Ciudad. Bien, vamos a solucionarlo.
7.  Abrir el **Editor de Consultas** en la pestaña **Inicio**. Seleccionar la columna **Ciudad**. Hacer click en **Reemplazar valores**. `ASTURIAS por GIJON`.
8.  Hacer Click en **Cerrar y Aplicar**

9.  Finalmente añadamos el **Tipo de Máquina** como leyenda en ambos gráficos.

10.  Renombramos *Página 1* como *MyFirstReport*

11.  Vamos a **Archivo** -> **Guardar**.


Power BI Service
-------------

1.  Go to <http://www.powerbi.com> or <https://app.powerbi.com> para explorar el informe.

2.  Hacer click en *Anclar elemento activo*. Crear un nuevo cuadro de mando llamado *myFirtsDashboard*

3.  **Intenta hacer una pregunta en Lenguaje Natural (Naturalmente Inglés :) )**

`Show importe in Tenerife` `Show importe in MAdrid and Barcelona`

Ejercicios Adicionales
-------------

1. Prueba a buscar información rápida en el conjunto de datos en Power BI Service. Para ello, colocate sobre el icono de los **...** al lado del conjunto de datos en Power BI Service. Haz click sobre *INFORMACIÓN RÁPIDA*
2. Prueba a buscar **exportar los datos de una visualización hacia MS Excel**. Para ello, colocate sobre el icono de los **...** al lado de la visualización del gráfico de barras. Haz click sobre *EXPORTAR DATOS A EXCEL*
