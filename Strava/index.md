# Strava Dashboard Project

**[Link Repositorio Github](https://github.com/arnaugr55/Strava_project)**<br>
**[Link Strava](https://www.strava.com/)**

En este proyecto he descargado mi archivo strava que contiene información de mis actividades y otras estadísticas de mi cuenta Strava [aquí](https://www.strava.com/athlete/delete_your_account). Con estos datos, y usando python he creado varios datasets con los que me he hecho un Dashboard interactivo, con Power BI.

***Código***<br>
1. script_principal.py: Itera los ficheros gpx de cada actividad 1 a 1 y va guardando la información de en que municipios se ha pasado (poblacions.csv) y en que montañas se han subido (mountains.csv).
2. activities_csv.py: Con el csv activities (que es uno de los documentos que da Strava al descargar la info), he hecho algunas modificaciones para adaptarlo al formato excel.
3. create_json_gpx.py: Iteramos de nuevo el gpx de cada actividad y guardamos los puntos (coordenadas) en un JSON.
4. poblacions.py: A partir del poblacions.csv, crea 2 nuevos datasets (poblacions2.csv y poblacions3.csv) con su información.
Estos ficheros generados los cargaremos posteriormente al dashboard de Power BI.

Los scripts se encuentran en el github del proyecto. Ahí están comentados paso a paso.

***Dashboard***<br>
Con la información recogida, he creado un dashboard de 2 pestañas.<br>

--Pestaña General--<br>
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Strava/resources/captura_01.png" alt="Primera Pestaña" width="850">
</div>

Gráficas e info:
- Panel de información con los totales (número de actividades, distancia, tiempo, desnivel positivo y montañas subidas).
- Mapa interactivo con todos los tracks de la ruta. Si nos colocamos sobre un punto, nos da la infromación sobre las coordenadas, la actividad, altitud (mts), fecha y hora y km de la actividad.
- Paneles con la actividad con + distancia, + rápida, + desnivel positivo y + duradera.
- Tabla con la información de todas las actividades. Contiene las columnas Actividad, Fecha y hora, Desnivel positivo, Distancia, Velocidad Mediana, Tiempo en Movimiento, Tiempo Transcurrido y Montañas. Por defecto viene ordenado por la fecha de la actividad, pero se puede cambiar y ordenar por cualquiera de estas columnas.
- Ranking geográfico de municipios, comarcas y provincias con más KMs recorridos.
 
Filtros:
- Por la fecha de la actividad.
- Por la distancia mínima o máxima de la actividad.
- En el ranking geográfico, si seleccionamos un territorio (municipio, comarca o provincia), nos saldrán solo las rutas en las que se haya pasado por aquel territorio.
- En la tabla, se puede seleccionar una actividad, para que filtre por esa actividad.
Todos estos filtros afectan a las actividades que se muestran.

Otros:
- Panel para acceder a la otra pestaña (Mapas y Estadísticas) con un Ctrl+Clic.

<br>--Pestaña Mapas & Estadísticas--<br>
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Strava/resources/captura_02.png" alt="Primera Pestaña" width="850">
</div>

Gráficas e info:
- Mapa interactivo con las montañas subidas. Para cada montaña, da la información de la altitud, número de veces subida, distancia máxima hasta la cima, tiempo mínimo hasta la cima y desnivel acumulado máximo hasta la cima. Además, para cada vez subida muestra la actividad, la fecha y hora de la cima.
- Gráfica de tiempo (días) en actividades por mes.
- Gráfica de tiempo (días) en actividades por año.
- Gráfica de distancia (kms) por mes.
- Gráfica de distancia (kms) por año.
- Gráfica con las horas del día en las que se han hecho más kms.
- Mapa de municipios recorridos por comarca. Como más oscura sea la comarca, más alto es el porcentaje de municipios recorridos.
- Mapa de municipios recorridos. Como más oscuro sea el municipio, más kms se han recorrido en él. Recomendable ponerlo en pantalla grande para una mejor visualización.

Filtros:
- Por la fecha de la actividad.
- En las gráficas de año o mes, se puede seleccionar un año o mes, para que filtre ese año o mes.
- En los mapas de municipio, se puede seleccionar un municipio o comarca, para que filtre ese municipio o comarca.
Todos estos filtros afectan a las actividades que se muestran.

<br>Aquí está el video de su funcionamiento publicado en LinkedIn:

<div style="text-align: center;">
    <iframe src="https://www.linkedin.com/embed/feed/update/urn:li:activity:7205284381215625216" height="500" width="640" frameborder="0" allowfullscreen="" title="Publicación integrada"></iframe>
</div>

**Si encontráis interesante el proyecto y queréis tenerlo también para vuestros datos, no dudéis en contactar conmigo y os resuelvo las dudas, vemos como lo podemos hacer...**
