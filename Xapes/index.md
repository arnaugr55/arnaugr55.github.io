# Xapes

<div class="tabs">
  <ul>
    <li><a href="../">Inicio</a></li>
    <li><a href="/Strava/">Strava Project</a></li>
    <li><a href="/Simulació UCL/">Simulació UCL</a></li>
    <li><a href="/Flags_Similarity/">Flags Similarity</a></li>
    <li><a href="/Xapes/">Xapes</a></li>
    <li><a href="/Wordle_Solver/">Wordle</a></li>
    <li><a href="/Puzzle_Solver/">Puzzle</a></li>
  </ul>
</div>
<link rel="stylesheet" href="/custom.css"><br>

**Publicación**: 22/02/2026<br>
--> **[Link Repositorio Github](https://github.com/arnaugr55/Xapes)**<br>
--> **[Link Xapes.net](https://www.xapes.net/ca/)**<br>
--> **[Explicación coleccionismo de placas/chapas de cava](https://es.wikipedia.org/wiki/Placas_de_cava)**

## Idea<br>
Desde pequeño, tengo una colección heredada de xapes de cava. Esta afición la he ido perdiendo con los años, pero desde hace unos 2 años aprox. que retomé la afición. El último verano fui a un intercambio (sí, yo ahí con gente que me triplicaba la edad) y, aunque conseguí cambiar alguna que otra chapa, me dieron una recomendación que me dio la idea del proyecto.

<i>**No hace falta que lleves todas las repetidas que tienes, ya que hay muchas chapas que las tiene todo el mundo.**</i>


Claro, y yo con 2 álbumes gigantes llenos de chapas, las cuales un 80% no servían de nada. Entonces, decidí descartar las típicas. Pero, aunque más o menos sé cuáles son, decidí cuantificarlas y darles una puntuación a todas las chapas, para ver cada chapa, cuán"típica" es. Y poder, así, descartar las más típicas, que para intercambiar... pues no me sirven. **¡¡Ahí nació este proyecto!!**


## Detalles y funcionalidades<br>
El proyecto cuenta con 6 scripts. Los 6, en Python, que es el lenguaje que domino más. Estos ".py" están numerados con el orden que se debe seguir. No hay una dependencia lineal entre cada uno de ellos, pero sí es recomendable seguir este orden.

En total hay unas 4 funcionalidades, descritas a continuación:


**Scrapping de todas las chapas de xapes.net** (Script "1. extract_xapes.py")<br>
La web de xapes.net, entre otras cosas, contiene información de todas las chapas que hay (la verdad es que está muy bien organizado). Parte de esta información son el núm. de usuarios que tienen esa chapa en la colección y el núm. de usuarios que la tienen repetida. Con esos 2 valores he calculado la puntuación de cada chapa, con la siguiente fórmula:
<i>Puntuación = Num_colección + Num_repetidas*2</i> 

Así, iterando +200.000 chapas, he generado el "Excel_xapes.xlsx" que contiene, para cada chapa: su id, Cava (colección), Num_colección, Num_repetidas, Puntuación, Anyomes en la que se ha hecho su carga y un campo "Colección", que he rellenado posteriormente, en el que he indicado como "Sí" aquellas chapas qu tengo en la colección.

<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Xapes/resources/Excel_xapes_exemple.png" alt="Primeras lineas de Excel_xapes" width="600">
</div>

<i>En amarillo he marcado las chapas que, como las tenía como repetidas (y varias veces), las he descartado del álbum de repetidas.</i> 

Mencionar que cada vez van apareciendo más chapas y se van registrando en xapes.net. Así que, en un futuro, volveré a lanzar el scrappeo, añadiendo estas nuevas chapas y actualizando las ya existentes (quizás no todas), ya que es probable que su puntuación se haya visto modificada. Es por eso que es importante el campo ANYOMES, para ver cuándo se actualizó esa chapa por última vez.<br>


**Visualización de las chapas** (Script "2. genera_imatges.py")<br>
De cara a ir haciendo el inventario de las chapas que tengo o no tengo en mi colección, he tenido que ver imágenes de las chapas (ya que, si no, es imposible). En vez de ir entrando en las URLs de xapes.net manualmente, he implementado un script que, dada una lista de IDs de chapas, me las descarga todas en una carpeta local:

Así he podido hacer cosas como:
- Filtrar en el "Excel_xapes.xlsx" por las chapas de x Cava y, usando sus ids, obtener todas sus chapas.
- Filtrar en el "Excel_xapes.xlsx" por las chapas más importantes que no tengo y, usando sus IDs, obtener todas las chapas.

<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Xapes/resources/Carpeta_imatges_xapes.png" alt="Carpeta de imágenes con 4 chapas de ejemplo" width="600">
</div><br>


**Mapa de cavas & Co.** (Scripts "3. estadistiques_xapes.py", "4. comarc_prov.py" y "5. xapes_mapa.py")<br>
Agrupamos todas las chapas por colección/cava y, para cada una de estas colecciones, la localizamos en un municipio, comarca y provincia, además de darle una puntuación. Cogemos solo las 1000 cavas/colecciones con más puntuación.
- La puntuación se obtiene según el número de chapas y la puntuación de estas.
- El municipio lo obtenemos de nuevo, scrappeando el xapes.net.
- La comarca y provincia se obtienen cruzando con un CSV local donde tenemos esa relación de municipio, comarca y prov.

A la hora de scrappear el municipio del propio xapes.net, nos hemos encontrado que había cavas de las cuales no tenía su municipio o estaba escrito incorrectamente. Estos los hemos tenido que modificar manualmente.

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
    <iframe id="map-iframe" src="https://arnaugr55.github.io/Xapes/resources/mapa_caves_20251213.html" style="width: 100%; height: 500px; border: none;"></iframe>
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
</style><br>


**Probabilidades de chapa repetida** (Script "6. probs_xapes.py")<br>
Esta funcionalidad nació de la curiosidad de saber, al abrir una ampolla, sabiendo de qué cava es, cuál es la probabilidad de que esa chapa sea repetida o no. De eso trata este script, que me da una probabilidad para las colecciones en las que tengo, mínimo, una chapa. Los factores para dar más o menos probabilidad son los siguientes:
- Número de chapas de la colección/cava VS número de chapas de esa colección/cava que Sí tengo.
- Importancia de cada chapa (cuanto más importante es, más fácil es que la pueda obtener).
- Fecha de la chapa. (Si es una chapa muy antigua, es probable que ya no se produzca. Y al revés).

<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Xapes/resources/probs_xapes_output.png" alt="Porbabilidades de algunas marcas" width="400">
</div>
