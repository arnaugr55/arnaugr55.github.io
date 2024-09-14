#  Arnau Garriga Riba <br />- Data Science Portfolio

En este Portfolio hago una compilación de todos los proyectos hechos. Algunos en la universidad y otros ya en mis tiempos libres por auto-aprendizaje.

- **Email**: [agarrigariba@gmail.com](agarrigariba@gmail.com)
- **LinkedIn**: [linkedin.com/arnau-garriga-riba-9304a5216](https://www.linkedin.com/in/arnau-garriga-riba-9304a5216/)
- **Github**: [github.com/arnaugr55/](https://github.com/arnaugr55)


## Mis mejores Proyectos


**[Flags Similarity](https://github.com/arnaugr55/Flags-Similarity)**

En este proyecto se ha cogido un csv con información de las banderas de todos los países del mundo. Esta información consiste en características, como número de rayas verticales, número de rayas horizontales, color más predominante, número de estrellas...

En el Jupyter Notebook de **Python** (Graph representations of flags similarity.ipynb) se explica más en detalle todo el proyecto y se realiza lo siguiente:
- Se entrena un modelo de KNN10, para encontrar, para cada bandera, sus otras 10 banderas más similares.
- El usuario puede entrar una bandera, y con los resultados del KNN, muestra las otras 10 banderas similares a ella. Por orden.
- Se hacen una serie de grafos en los que he jugado con los resultados.


**[Wordle Solver](https://github.com/arnaugr55/Wordle-solver)**

Worlde tiene un total de 2316 soluciones. En este Jupyter Notebook de **Python**, te va diciendo, en cada paso, la mejor palabra a entrar hasta que encuentra la palabra que será la palabra del día. 

Tras entrar la palabra, se tiene que especifar el resultado, para que el algoritmo pueda encontrar la mejor siguiente palabra.


**[Puzzle_solver-CAT](https://github.com/arnaugr55/Puzzle_solver-CAT-)**

Proyecto de Computer Vision, en el cual, separa las 35 piezas de un puzzle 7*5 en fotos separadas y es capaz de resolver el puzzle colocando estas piezas en su posición correcta.

En este proyecto se ha usado el lenguaje M, y se ha desarrollado con **MATLAB**.


**[Strava-Dashboard-Project](https://github.com/arnaugr55/Strava_project)**

En este proyecto he descargado mi archivo strava que contiene información de mis actividades y otras estadísticas de mi cuenta Strava (https://www.strava.com/athlete/delete_your_account). Con este, y usando python he creado varios datasets con los que me he hecho un Dashboard interactivo, con Power BI.

***Código***
1. script_principal.py: Itera los ficheros gpx de cada actividad 1 a 1 y va guardando la información de en que municipios se ha pasado (poblacions.csv) y en que montañas se han subido (mountains.csv).
2. activities_csv.py: Con el csv activities (que es uno de los documentos que da Strava al descargar la info), he hecho algunas modificaciones para adaptarlo al formato excel.
3. create_json_gpx.py: Iteramos de nuevo el gpx de cada actividad y guardamos los puntos (coordenadas) en un JSON.
4. poblacions.py: A partir del poblacions.csv, crea 2 nuevos datasets (poblacions2.csv y poblacions3.csv) con su información.
Estos ficheros generados los cargaremos posteriormente al dashboard de Power BI.

***Dahshboard***
Con la información recogida, he creado un dashboard de 2 pestañas.
- En la primera hay la información general, un mapa con los recorridos de todas las actividades (o los seleccionados) e infromación de kms recorridos por Localidad (poblaciones, comarcas y provincias catalanas).
- La segunda consiste en un conjunto de gráficas y mapas. En uno de los mapas podemos ver las montañas subidas con información de estas.


**[Spotify Catalunya Data]**

Proyecto en el cual estoy trabajando. De momento muestro, como aperitivo, un mapa generado.
<iframe src="https://arnaugr55.github.io/images/mapa_artistes_20240909.html" 
        width="100%" height="400" frameborder="0" style="border:0;" allowfullscreen>
</iframe>

<div id="map-container" style="position: relative; text-align: center;">
    <!-- Fullscreen Icon (Enter Fullscreen) -->
    <img id="fullscreen-icon" src="https://img.icons8.com/ios-filled/50/000000/full-screen.png" 
         alt="Enter Fullscreen" 
         onclick="toggleFullscreen()" 
         style="position: absolute; top: 10px; right: 10px; cursor: pointer; z-index: 1000; width: 30px; height: 30px;">

    <!-- Exit Fullscreen Icon (Visible only in fullscreen) -->
    <img id="exit-fullscreen-icon" src="https://img.icons8.com/ios-filled/50/000000/collapse.png" 
         alt="Exit Fullscreen" 
         onclick="toggleFullscreen()" 
         style="position: absolute; top: 10px; right: 10px; cursor: pointer; z-index: 1000; width: 30px; height: 30px; display: none;">

    <!-- Embed your Folium map using an iframe -->
    <iframe id="map-iframe" src="https://arnaugr55.github.io/images/mapa_artistes_20240909.html" style="width: 100%; height: 500px; border: none;"></iframe>
</div>

<script>
    // JavaScript to toggle fullscreen
    function toggleFullscreen() {
        var mapContainer = document.getElementById('map-container');
        var fullscreenIcon = document.getElementById('fullscreen-icon');
        var exitFullscreenIcon = document.getElementById('exit-fullscreen-icon');

        if (mapContainer) {
            // Toggle fullscreen mode
            mapContainer.classList.toggle('fullscreen');

            // Toggle icons visibility
            if (mapContainer.classList.contains('fullscreen')) {
                fullscreenIcon.style.display = 'none';
                exitFullscreenIcon.style.display = 'block';
            } else {
                fullscreenIcon.style.display = 'block';
                exitFullscreenIcon.style.display = 'none';
            }
        }
    }
</script>

<style>
    /* Fullscreen styling */
    #map-container.fullscreen #map-iframe {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 9999;
        background-color: white;
    }
</style>
