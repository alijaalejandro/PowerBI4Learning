Lab 1. Ejemplo de conexión a servicios SaaS desde Power BI Service
================

Introducción
------------

*Nota* Extraido de https://powerbi.microsoft.com/es-es/documentation/powerbi-content-packs-services/

Puede conectarse a los paquetes de contenido de varios servicios que usa para dirigir su empresa, como Salesforce, Microsoft Dynamics y Google Analytics. Power BI comienza usando sus credenciales para conectarse al servicio y después crea un panel de Power BI y un conjunto de informes de Power BI que muestran sus datos automáticamente y proporcionan información visual acerca de su empresa.

Vea todos los paquetes de contenido de servicios iniciando sesión en Power BI. El equipo de Power BI está trabajando con otros servicios para agregar nuevos paquetes de contenido cada semana.

![imágen de los diferentes servicios SaaS de Power BI] (https://dpspowerbi.blob.core.windows.net/powerbi-prod-media/powerbi.microsoft.com/es-es/documentation/articles/powerbi-content-packs-services/20160804075537/overview.png)

Qué se incluye
------------
Después de conectarse a un paquete de contenido, verá un panel, un informe y un conjunto de datos recién creados. Los paquetes de contenido incluyen contenido desde el servicio que se centra en un escenario concreto y no incluyen toda la información del servicio. Después de la importación, puede personalizarlos para resaltar la información que más le interese. Se han programado los datos para que se actualicen automáticamente una vez al día. Puede controlar la programación seleccionando el conjunto de datos.

También puede usar Power BI Desktop para conectarse a algunos servicios, como Google Analytics y crear sus propios informes y paneles personalizados.

Para obtener más detalles sobre un paquete de contenido específico, consulte las páginas de ayuda individuales.

Veamos un ejemplo
------------
En este caso, vamos a conectar con el CRM corporativo de la empresa Izertis.
*Nota: este paquete de contenido se usa sólamente a efectos de ejemplo puesto que la información que contiene es información sensible de una empresa*.

1. Iniciamos sesión en Power BI Service.
2. Hacemos click en **Obtener Datos** ![Obtener Datos] (https://dpspowerbi.blob.core.windows.net/powerbi-prod-media/powerbi.microsoft.com/en-us/documentation/articles/powerbi-service-get-data/20160706081314/pbi_getdata_startscreen.png)

3. Buscamos el servicio **Microsoft Dynamics CRM Online Sales Manager** y hacemos click en **Obtener**
4. Escribimos la dirección del servicio `https://izertis.api.crm4.dynamics.com` y seleccionamos autenticación de tipo **OAuth2**
5. Si la introducción de las creedenciales ha sido correcta pronto veremos la actualización. 

![Imagen de CRM Online][CRM]

[CRM]: CRM_SaaS.PNG

Juguemos alrredor de este conjunto de Datos
------------
Veamos por ejemplo como enviar los datos de CRM a una Tabla dinámica de MS Excel.

BING como servicio SaaS
------------
![Imágen de Bing][BING]

[BING]: BING_SaaS.PNG

Probar con la palabra clave **ISIS**

Probemos GuitHub
------------



