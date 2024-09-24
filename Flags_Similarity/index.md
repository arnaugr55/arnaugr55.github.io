# Flags Similarity Project

<div class="tabs">
  <ul>
    <li><a href="../">Inicio</a></li>
    <li><a href="/Strava/">Strava Project</a></li>
    <li><a href="/Flags_Similarity/">Flags Similarity</a></li>
  </ul>
</div>
<link rel="stylesheet" href="/custom.css"><br>

**Publicación**: 19/02/2023<br>
--> **[Link Repositorio Github](Flags-Similarity)**<br>

***Información***<br>
Proyecto realizado en un notebook de python (.ipynb). En el notebook tenemos un grupo de gráficos que muestran la similitud entre las banderas de los 214 países y territorios. Esta similitud se ha encontrado mediante un modelo de KNN.

El conjunto de datos utilizado tiene información de algunas características del país (masa continental, zona, área, población, idioma y religión) y también información sobre la bandera (barras, n_rayas, n_círculos...). Se ha obtenido de [esta web](https://archive.ics.uci.edu/ml/datasets/Flags).

El conjunto de datos se realizó en 1986, por lo que está muy desactualizado. Sabiendo eso, he modificado el conjunto de datos:
- Añadiendo algunos países que no existían en ese momento (Rusia, Serbia, Lituania...).
- Eliminando los países que ya no existen.
- Actualizando las banderas que se han cambiado recientemente (Mauritania, Venezuela, Malawi...).
- Actualizando la información que necesitaré para algunos gráficos (masa continental y población).
- Además, he cambiado el criterio de la variable 23 (estrellas solares). En lugar de contar la cantidad de soles o estrellas, el valor de las columnas es:
  - 0 -> Si no hay soles o estrellas
  - 1 -> Si tiene un sol o una estrella
  - 2 -> Si tiene varios soles o estrellas

***Código***<br>
El código se encuentra en el fichero *Graph representations of flags similarity.ipynb* del repositorio. Se encuentra explicado en inglés paso a paso.

<br>***Dataset***<br>
El dataset de entrada con la información de cada país y de su bandera es el siguiente:
<iframe src="https://arnaugr55.github.io/Flags_Similarity/resources/banderas_paises.html" width="100%" height="500px"></iframe>

<br>

<br>***Resultados***<br>
--TOP10 Similitudes--<br>
Con un KNN calculamos las 10 banderas/vecinos más parecidos para cada una. El usuario puede entrar el país y obtendrá las 10 banderas más parecidas a la del país seleccionado:
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Flags_Similarity/resources/top10_similitud.png" alt="España y banderas similares" width="850">
</div>
Como vemos en este ejemplo, la bandera de España es similar a otras banderas con franjas horizontales, colores rojizos, símbolos en el medio...


--Grafos Generados--<br>
Se han generado un total de 6 grafos. Son los siguientes.
<iframe src="https://arnaugr55.github.io/Flags_Similarity/resources/grafos_banderas_tabla.html" width="100%" height="500px"></iframe>


Además, en el notebook también podemos ver que se han hecho análisis (xxxx) sobre los resultados. 


