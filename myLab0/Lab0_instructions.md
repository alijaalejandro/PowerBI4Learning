Lab 0. E2E Solution based on Power BI
================

Introducción
------------

En este laboratorio de introducción vamos a ejemplificar un flujo de datos completo en Power BI. Desde la carga original de un conjunto de datos en formato MS Excel hasta la creación de un cuadro de mando personalizado en Power BI service.

Instrucciones
-------------

IMPORTANTE! Antes de emprezar.

1.  Ejecute la aplicación Power BI Desktop. *Recuerde que si no lo ha hecho aun puede descargar Power BI gratuitamente en <https://powerbi.microsoft.com/en-us/downloads> *

2.  Actualiar la configuración regional. *Recordar que esta opción se encuentra en el menú de Opciones*

3.  Localizar el fichero de datos de MS Excel *myRENT\_1k.xlsx* en el directorio de correspondiente al Lab0 de este curso. Si tiene problemas para localizar este directorio recuerde que puede encontrar toda la información de este curso en <https://github.com/alijaalejandro/PowerBI4Learning>.

4.  Hacer click en Get Data --&gt; Seleccionar tipo de fichero csv

<!-- -->

    ##             Empresa      Actividad.Económica Cliente
    ## 1 HUNE RENTAL, S.L. INSTALACIONES ELÉCTRICAS    1008
    ## 2 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119
    ## 3 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119
    ## 4 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119
    ## 5 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119
    ## 6 HUNE RENTAL, S.L.    SERVICIOS: Rotulistas   10119

1.  Click on Edit para observar qué ocurre.

*A continuación se abrirá una nueva pantalla denominada el Query Editor. Este módulo es el encargado de permitir el modelado avanzado de datos con Power BI. Con este módulo podrémos realizar transformaciones a los datos, agregaciones, adaptaciones de formato, etc.*

Detengámonos un momento a observar las diferentes partes de este módulo. Volveremos con más detalle sobre este módulo en el capítulo 3 sobre modelado avanzado de datos con Power BI.

1.  Apliquemos algunas transformaciones básicas.

Click on Transform -&gt; Count Rowsw

-   **Pregunta 1**. ¿Cuantas filas tiene este conjunto de datos?
-   **Pregunta 2**. Como puedes observar, Power BI ha identificado automaticamente el tipo de datos que contienen las columnas del conjunto de datos (Inferencia automática del Esquema) ¿Ha sido correcta esta asignación?

1.  Hacer click en **close&apply**

2.  Observamos la vista de Power BI Desktop. Disponemos de 3 modos de visualización: **Report**, **Data** y **Relationships**.

3.  Pasamos a modo **Data** y formateamos adecuadamente

4.  Pasamos a modo **Report** Renombramos el Report **MyRent Report**.

5.  Hacemos un **Bar Chart** con importe vs Delegación sorted by Importe.

6.  Hacemos un **Map Plot** con importe by delegación. **Upps!. Doesn\`t work**

Explicación: Power BI tiene cierta inteligencia para detectar datos geográficos, como continentes, paises, ciudades, códigos postales, etc. Sin embargo, como sabéis, los nombres de ciudades no son únicos alrrededor del mundo. Lo ideal es trabajar con indentificadores únicos como códigos postales dentro de un pais o latitud y longitud en todo el mundo. Lo que ocurre es que, en el mundo real, a verces no disponemos de toda la información en perfecto estado. Por eso debemos de aplicar algunos trucos para obtener el resultado más próximo a lo que buscamos.

Vamos a ver una posible solución a este problema en concreto. Además aprovecharemos para introducir el tema de las **Jerarquías** en Power BI.

1.  Volvamos a la vista **Data** y creemos una nueva columna llamada **Country**. Fijemos el valor de country a la constante *Spain*. Categoricemos esta nueva variable como tipo **Country**

`Country = "Spain"`

1.  Renombremos la columna **Delegación** como **City**. Categoricemos como **City**

2.  Volvamos a la vista **Report** y creemos una jerarquía lógica **Country -&gt; City**. Para ello, debemos arrastrar el campo **city** dentro de **Country**

3.  Hagamos de nuevo el Map Plot en este caso utilizando la nueva variable creada como jerarquía.

4.  Finalmente añadamos el **Tipo de Obra** como leyenda en ambos gráficos.

5.  Renombramos *Page 1* como *MyFirstReport*

6.  Click on Save as *MyFirstReport*

7.  Go to <http://www.powerbi.com> or <https://app.powerbi.com> para explorar el informe.

8.  Hacer click en *Anclar elemento activo*. Crear un nuevo cuadro de mando llamado *myFirtsDashboard*

9.  **Intenta hacer una pregunta en Lenguaje Natural (Naturalmente Inglés :) )**

`Show importe in Tenerife` `Show importe in MAdrid and Barcelona`
