# Strava Dashboard Project

**[Link Repositorio Github](https://github.com/arnaugr55/Strava_project))**<br>
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
Con la información recogida, he creado un dashboard de 2 pestañas.
Pestaña General<br>
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Strava/resources/captura_01.png" alt="Primera Pestaña" width="850">
</div>
Gráficas e info:
 - Panel de información con los totales (número de actividades, distancia, tiempo, desnivel psoitivo y montañas subidas).
 - Mapa interactivo con todos los tracks de la ruta. Si nos colocamos sobre un punto, nos da la infromacióm sobre las coordenadas, la actividad, altitud (mts), fecha y hora y km de la actividad.
 - Paneles con la actividad con + distancia, + rápida, + desnivel positivo y + duradera.
 - Tabla con la información de todas las actividades. Contiene las columnas Actividad, Fecha y hora, Desnivel positivo, Distancia, Velocidad Mediana, Tiempo en Movimiento, Tiempo Transcurrido y Montañas.
 - Ranking geográfico de municipios, comarcas y provincias con más KMs recorridos.
Filtros:
- 
Otros:
- 

- La segunda consiste en un conjunto de gráficas y mapas. En uno de los mapas podemos ver las montañas subidas con información de estas.<br>
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Strava/resources/captura_02.png" alt="Primera Pestaña" width="850">
</div>

**Si encontráis interesante el proyecto y queréis tenerlo también para vuestros datos, no dudéis en contactar conmigo y os resuelvo las dudas, vemos como lo podemos hacer...**
