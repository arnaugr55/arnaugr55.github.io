# Strava Dashboard Project

**[Link Repositorio Github]([Strava/](https://github.com/arnaugr55/Strava_project))**<br>
**[Link Strava](https://www.strava.com/)**

En este proyecto he descargado mi archivo strava que contiene información de mis actividades y otras estadísticas de mi cuenta Strava [aquí](https://www.strava.com/athlete/delete_your_account). Con este, y usando python he creado varios datasets con los que me he hecho un Dashboard interactivo, con Power BI.

***Código***<br>
1. script_principal.py: Itera los ficheros gpx de cada actividad 1 a 1 y va guardando la información de en que municipios se ha pasado (poblacions.csv) y en que montañas se han subido (mountains.csv).
2. activities_csv.py: Con el csv activities (que es uno de los documentos que da Strava al descargar la info), he hecho algunas modificaciones para adaptarlo al formato excel.
3. create_json_gpx.py: Iteramos de nuevo el gpx de cada actividad y guardamos los puntos (coordenadas) en un JSON.
4. poblacions.py: A partir del poblacions.csv, crea 2 nuevos datasets (poblacions2.csv y poblacions3.csv) con su información.
Estos ficheros generados los cargaremos posteriormente al dashboard de Power BI.

***Dashboard***<br>
Con la información recogida, he creado un dashboard de 2 pestañas.
- En la primera hay la información general, un mapa con los recorridos de todas las actividades (o los seleccionados) e infromación de kms recorridos por Localidad (poblaciones, comarcas y provincias catalanas).<br>
  <img src="https://arnaugr55.github.io/Strava/resources/captura_01.png" alt="Primera Pestaña" width="600">
- La segunda consiste en un conjunto de gráficas y mapas. En uno de los mapas podemos ver las montañas subidas con información de estas.<br>
  <img src="https://arnaugr55.github.io/Strava/resources/captura_02.png" alt="Primera Pestaña" width="600">
