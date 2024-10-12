# Flags Similarity Project

<div class="tabs">
  <ul>
    <li><a href="../">Inicio</a></li>
    <li><a href="/Strava/">Strava Project</a></li>
    <li><a href="/Flags_Similarity/">Flags Similarity</a></li>
    <li><a href="/Wordle_Solver/">Wordle</a></li>
  </ul>
</div>
<link rel="stylesheet" href="/custom.css"><br>

**Publicación**: 11/12/2022<br>
--> **[Link Repositorio Github](https://github.com/arnaugr55/Wordle-solver)**<br>

***Información***<br>
Este proyecto consiste en un notebook de python (.ipynb) que te va diciendo, en cada ronda, cual es la mejor palabra para entrar en el [Wordle Inglés](https://www.nytimes.com/games/wordle/index.html).

**Ejemeplo de como funciona:**<br>
Siempre empezamos con la palabra "SOARE", que, por combinación de letras es la mejor a entrar, según el algoritmo. Tras esto, entramos el resultado de los 5 colores obtenidos en el código (Green='G', Yellow='Y', Gray='B'). Según estos resultados, el algoritmo recalculará la mejor palabra a entrar, la entramos y escribimos el resultado... Y así vamos haciendo hasta que el algoritmo encuentra la palabra..

**Datasets de Entrada:**<br>
Resulta que el Worlde tiene un total de 12974 palabras a entrar, pero de estas, solo 2316 pueden ser la solución. Es decir, hay palabras que puedes poner, pero que nunca serán la solución final.
Estos palabras se encuentran en los csvs valid_solutions (2316 que pueden ser solución) y valid_guesses (10658 que NO pueden ser solución) obtenidos de [kaggle](https://www.kaggle.com/datasets/bcruise/wordle-valid-words) y guardados en mi repositorio github.

**Algoritmo para encontrar la siguiente mejor palabra:**<br>
El algoritmo tiene en cuenta la frecuencia de las letras, tanto en general como por posición (frecuencia para cada una de las 5 posiciones).
Estas frecuencias las calcula en cada iteración. Es decir, una vez tengamos el primer resultado, ya tendremos varias palabras descartadas, así que solo calcularemos la frecuencia de estas posibles palabras que encajan con el resultado.>br>
<br>Las palabras que se van entrando son valid_guesses
>Cuando el algoritmo ve que quedan s 
