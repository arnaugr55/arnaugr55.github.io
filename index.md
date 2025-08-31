<div class="tabs">
  <ul>
    <li><a href="#home">Inicio</a></li>
    <li><a href="/Strava/">Strava Project</a></li>
    <li><a href="/Simulació UCL/">Simulació UCL</a></li>
    <li><a href="/Flags_Similarity/">Flags Similarity</a></li>
    <li><a href="/Wordle_Solver/">Wordle</a></li>
    <li><a href="/Puzzle_Solver/">Puzzle</a></li>
  </ul>
</div>
<link rel="stylesheet" href="/custom.css">

#  Arnau Garriga Riba <br />- Data Science Portfolio

En este Portfolio hago una compilación de todos los proyectos hechos. Algunos en la universidad y otros ya en mis tiempos libres por auto-aprendizaje.

- **Email**: [agarrigariba@gmail.com](agarrigariba@gmail.com)
- **LinkedIn**: [linkedin.com/arnau-garriga-riba-9304a5216](https://www.linkedin.com/in/arnau-garriga-riba-9304a5216/)
- **Github**: [github.com/arnaugr55/](https://github.com/arnaugr55)


## Mis mejores Proyectos


**[Strava-Dashboard-Project](Strava/)**

Proyecto de Python + Power BI con la información que da la red social de deportes, Strava, sobre las actividades hechas.

Mediante Power BI he creado un dashboard interactivo donde se pueden ver los recorridos realizados, total de kilómetros o actividades, montañas subidas por mi propio usuario.

Para adaptar y transformar los datos obtenidos he usado Python.


**[Simulacio-UCL](Simulacio_UCL/)**

Proyecto de código Python en el que he programado el desarrollo de la Champions League. Desde la definidión de los 144 partidos de la Fase Liga hasta la final.

Se ha usado la librería de Flask para mostrar la clasificación y los resultados en un html en el navegador. Además, también se ha usado la librería PIL para mostrar en imágenes, los contrincantes de cada equipo en la fase liga y el bracket de las ronda eliminatoria.

El proyecto tabién cuenta con la opción de lanzar vasrias simulaiones una tras otra. Tras esto, devuelve un csv con los resultados de cada equipo en cada iteración.


**[Flags Similarity](Flags_Similarity/)**

En este proyecto se ha cogido un csv con información de las banderas de todos los países del mundo. Esta información consiste en características, como número de rayas verticales, número de rayas horizontales, color más predominante, número de estrellas...

En el Jupyter Notebook de **Python** (Graph representations of flags similarity.ipynb) se explica más en detalle todo el proyecto y se realiza lo siguiente:
- Se entrena un modelo de KNN10, para encontrar, para cada bandera, sus otras 10 banderas más similares.
- El usuario puede entrar una bandera, y con los resultados del KNN, muestra las otras 10 banderas similares a ella. Por orden.
- Se hacen una serie de grafos en los que he jugado con los resultados.<br>


**[Wordle Solver](https://github.com/arnaugr55/Wordle-solver)**

Worlde tiene un total de 2316 soluciones. En este Jupyter Notebook de **Python**, te va diciendo, en cada paso, la mejor palabra a entrar hasta que encuentra la palabra que será la palabra del día. 

Tras entrar la palabra, se tiene que especifar el resultado, para que el algoritmo pueda encontrar la mejor siguiente palabra.<br>


**[Puzzle_solver-CAT](https://github.com/arnaugr55/Puzzle_solver-CAT-)**

Proyecto de Computer Vision, en el cual, separa las 35 piezas de un puzzle 7*5 en fotos separadas y es capaz de resolver el puzzle colocando estas piezas en su posición correcta.

En este proyecto se ha usado el lenguaje M, y se ha desarrollado con **MATLAB**.<br>


**Spotify Catalunya Data**

Proyecto en el cual estoy trabajando. De momento muestro, como aperitivo, un mapa generado.
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
    <iframe id="map-iframe" src="https://arnaugr55.github.io/resources/Spotify/mapa_artistes.html" style="width: 100%; height: 500px; border: none;"></iframe>
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


<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-TDPH3JHKE7"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-TDPH3JHKE7');
</script>
<!-- Fin de Google Analytics -->
