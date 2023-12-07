
<h1 align=center> **PROYECTO INDIVIDUAL Nº1** </h1>

<p align=center><img src=https://media.telemundoarizona.com/2019/09/shutterstock-accidente-aereo-cifras.jpg?quality=85&strip=all&resize=1200%2C675><p>

**Introducción:**
Desde el inicio de las civilizaciones el hombre ha querido imitar el comportamiento de los pájaros y conquistar el cielo. Primero en 1782 joseph y Jacques Montgolfier crearon el globo aerostático en Francia. Luego en 1852, también en Francia, Henri Giffard crea el primer modelo de dirigible. El italiano Enrico Forlanini creó el primer prototipo de helicóptero que alcanzaba los 13 metros de altura en 1877.  En Estados Unidos en el año 1903 Orville Wright crea el primer avión del mundo. Finalmente en 1957 la Unión Soviética lanza el primer satélite al espacio. Una interesante historia a través del tiempo que termina en el uso cotidiano y comercial de estos grandes inventos hoy en día pero ¿Serán seguros?  
En este proyecto nosotros somos un data analyst trabajando para la Organizacion de Aviación Civil Internacional (OACI) en el cual debemos analizar detalladamente los accidentes a lo largo de la historia viendo asi su cantidad, la fatalidad de los mismos y si las medidas realmente han funcionado. Las herramientas utilizadas para este trabajo han sido Python con las librerias Pandas e Ydataprofiling conjunto con Power Bi para crear gráficos de manera más acertiva para nuestro análisis. 
Es importante a medida que vemos nuestro dashboard leer el apartado de los KPI en este mismo README para entender mejor el análisis.

**Pasos del proyecto:**
1. *EDA*

Realizamos un análisis exploratorio de los datos en Python con Ydataprofiling. Allí vemos que existen muchos valores faltantes escritos con '?'. La detección de outliers lo hacemos en Power Bi. 

Las columnas de los datos son: fecha, hora registrada, Ruta (el lugar donde ocurrió el accidente), OperadOR (la institución a cargo del vehículo), flight_nro (número de vuelo), route (ruta de vuelo), ac_type (modelo del vehículo), registration (el registro donde se encuentra la especificación del avión, vuelo y tripulación), cn_ln (patente del vehículo), all_aboard (total de gente a bordo), cantidad de fallecidos (fallecidos totales), PASAJEROS A BORDO (cantidad de pasajeros), crew_aboard (tripulación a bordo), passenger_fatalities (pasajeros fallecidos), crew_fatalities (tripulantes fallecidos), ground (fallecidos en tierra) y finalmente summary (describe el accidente). Para destacar los pasajeros son civiles que consumen el servicio de transporte mientras que tripulación es la gente que trabaja en el vehículo. Las columnas cualitativas (aquellas que clasifican o describen cosas) son: Ruta, OperadOR, flight_no, Route, ac_type, registration, cn_ln, summary mientras que las columnas cuantitativas son: fecha, HORA declarada, all_abbard, PASAJEROS A BORDO, crew_aboard, cantidad de fallecidos, passenger_fatalities, crew_fatalities y ground. 

En el análisis exploratorio de los datos nos damos cuenta que algunas ciudades donde hay muchos accidentes son Moscow, New York, El Cairo, Manila y Sao Paulo. Los paises donde se repiten más palabras (lo que hace que sean donde más accidentes hay) son Rusia, Francia, Brasil, Inglaterra, México, Estados Unidos no aparece como tal pero aparecen muchas ciudades y estados como New York, Califonia o Alaska.
Las instituciones con más accidentes son Aeroflot (Rusia), Military - U.S. Air Force (Estados Unidos),Air France (Francia),Deutsche Lufthansa (Alemania) y United Air Lines (Estados Unidos).

También observamos que desde las 11 hs hasta las 17 hs se produce la mayor cantidad de accidentes. 

En general los aviones con más accidentes son los Douglas, sin embargo estos aviones fueron furor por la seguridad de los mismos por eso ses popularizó su uso. La cantidad de accidentes se debe a que eran los aviones mas usados durante el siglo XX.

En Power Bi vimos los outliers y el único valor atípico que encontramos es el de muertos en tierra, puntualmente en 2001 cuando ocurre el accidente de las torres gemelas. También vemos una gran correlación en los graficos de muertes por año y de cantidad de gente a bordo por año, lo que quiere decir que mientras más gente a bordo en cada accidente más muertos van a haber.

Finalmente la normalización de los datos (salvo de la columna hora hecha en python) la hicimos en Power Bi. Además en Power Bi hicimos un análisis más detallado para la implententación de los kpi.

**Aclaracion** Para ver el informe del EDA descargar y abrir el archivo informe_eda.html

2. *KPIS*

Primer KPI:

En este KPI analizaremos la última década (2010-2021) con respecto a la década anterior (2000-2009) para comparar la fatalidad de los accidentes y responder a la siguiente pregunta ¿Se ha reducido la fatalidad en un 10% como se habia propuesto?
Si bien vemos que los accidentes cayeron un 50,10% el porcentaje de personas fallecidas sobre el total a bordo aumentó de 56,28% a 60,74%. La fatalidad de la tripulación pasó de 3,28 por accidente a 3,75 por accidente. La fatalidad de los pasajeros también aumentó del 18,71 por accidente a 24,22 por accidente. Finalmente la fatalidad compuesta entre ambos pasó de 22,04 por accidente a 27,59 por accidente. Con estos análisis vemos que no se ha reducido lo esperado sino aumentado. Los accidentes son menos propensos pero cuando suceden son más fatales.


Segundo KPI:

Vemos a través del tiempo la cantidad de accidentes lo cual nos da pie al siguiente análisis histórico: "En los años 50 los vuelos comerciales han tomado popularidad por lo que se aumentó la utilización de aviones por ende también aumentaron los accidentes. En la década del 40 se crea motor a reacción lo que hace que el motor tire gas a una fuerza muy alta permitiendo el movimiento del avión, este invento hace que los aviones puedan volar más alto ya que necesitan grandes masas de aire para impulsarse por lo que hay mayor espacio para programar rutas y y evitar la coalisión además el aire ofrece menor resistencia por lo que se puede viajar mas rápido con menos combustible y no se crea una resistencia del aire que hace que el avión se frene. En 1958 se crea el primer avión comercial, el Boeing 707, con este tipo de motor que se populariza en la década del 60. Este evento en conjunto con el avance tecnológico de la caja negra, los radares de calor y los gps reducieron significativamente la cantidad de accidentes. 
En las décadas de los 80-90 hay una fuerte expansión a lo largo del mundo de grupos terroristas con motivos políticos y religiosos que tomaron como practica común la toma de aviones a modo de rehén lo cual causó en la década del 90 un pico de accidentes aéreos. 
En el año 2001 ocurre el atentado contra las torres gemelas o el llamado 911 (11 de septiembre) en el cual mundialmente se aumenta la seguridad aeroportuaria reduciendo significativamente los accidentes. 
El 14 de noviembre del año 2013 la OACI decreta el 'Anexo 19' que recomienda a los estados miembros distintos protocolos para manejar la seguridad operacional del avión, también así reduciendo los accidentes aéreos". En la década de los 80 hubo 553 accidentes y en los 90 hubo 631 lo que supone un aumento del 14,10% en los accidentes, con las medidas de seguridad aeroportuarias lo que esperamos es que en una década se reduzca de igual manera en la que subió. En la décadada de los 2000 se registraron 507 accidentes lo que supone una caida (con respecto a la década anterior, la de los 90) del 19,65%. El objetivo se cumplió con éxito y tenemos mejores resultados de los buscados.

Tercer KPI:

Aquí analizamos a Rusia que es uno de los paises com más accidentes aéreos. Vemos que repite los mismos patrones que el mundo con respecto a la cantidad de accidentes y fallecidos. También vemos que no existe correlación con los fallecidos en tierra sino que son accidentes aislados y no una falla del sistema. 
Su empresa más grande, Aeroflot, vemos que supone el 58,53% de los accidentes del pais por lo que hacemos un análisis sobre la empresa. Hasta la década del 90 vemos que la empresa se lleva casi todos los números de los accidentes totales pero con el paso del tiempo se van reduciendo. En la década de los 90 es donde se genera una "ruptura" de la tendencia donde en total hubo 41 accidentes de los cuales solo 9 fueron de Aeroflot entonces ¿Quién está a cargo del resto de accidentes? Analizando la década puntual vemos que hay unas 27 instituciones mientras que en la década de los 80 solo había 8 instituciones. Este suceso se debe a la caída de la Unión Soviética y la apertura de Rusia al mundo. Entonces Rusia quiere implementar con todas estas nuevas instituciones las mismas medidas con las que redujo los accidentes de Aeroflot con los mismos resultados entonces ¿Podrá lograrlo?
En los 60 contaban con 42 accidentes, en los 70 con 39 lo que da una reducción del 7,14% la primer década. En los años 80 hay 24 accidentes lo que corresponde una reducción del 38,46%  con respcto a la década anterior. Finalmente desde los 60 con 42 accidentes a los 80 con 24 accidentes supone una reducción del 42,86% que es lo que queremos para el resto de las empresas.
En los 90 tenemos 41 accidentes, en los 2000 ya contamos con 27 accidentes, una reducción del 34,14%. En la década de 2010 hay 23 accidentes, osea se redujo un 14,81%. Desde los 90 con 41 accidentes al 2021 con 23 accidentes vemos una reducción de 43,90% alcnzando así los objetivos esperados del  42,86%.

3. *Repaso*

Para cerrar hacemos un breve repaso sobre lo trabajado en los KPIS.

Vimos que los accidentes han disminuido significativamente (un 50,10%) pero la mortalidad de los mismos aumentó (de 18,04 por accidente a 24,22), esto quiere decir que son accidentes poco convencionales por lo que generan un mayor daño.

También dimos un pequeño vistazo a través de la historia para recalcar la importancia de aplicar protocolos de seguridad y como a medida que la tecnología avanza vamos reduciendo la cantidad de catástrofes. Con la nueva seguridad queríamos reducir un 14,10% los accidentes y se redujo en un 19,65%.

Finalmente hicimos un análisis sobre Rusia donde vimos como el país se abrió al ingreso de distintas empresas y estas al no tener los protocolos aplicados como en la empresa Aeroflot, generaban muchos accidentes. Rusia quería reducir los accidentes un 42,86% en dos décadas y los redujo en un 43,90%

Mi linkedin: https://www.linkedin.com/in/fabrizio-mazzucco-403b0825a
