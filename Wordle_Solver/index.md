# Wordle Similarity Project

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
Este proyecto consiste en un notebook de python (.ipynb) que te va diciendo, en cada ronda, cuál es la mejor palabra para entrar en el [Wordle Inglés](https://www.nytimes.com/games/wordle/index.html).

**Ejemplo de como funciona:**<br>
Siempre empezamos con la palabra "SOARE", que, por combinación de letras, es la mejor a entrar, según el algoritmo. Tras esto, entramos el resultado de los 5 colores obtenidos en el código (Green='G', Yellow='Y', Gray='B'). Según estos resultados, el algoritmo recalculará la mejor palabra a entrar. La entramos y escribimos el resultado... Y así vamos haciendo hasta que el algoritmo encuentra la palabra.
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Wordle_Solver/resources/Worlde_Solver_example.png" alt="Ejemplo de los pasos. Las flechas de derecha a izquierda indican que debemos entrar la palabra indicada en el Worlde, mientras que las otras flechas, indican que debemos escribir el resultado (colores) en el notebook." width="850">
</div>

**Datasets de Entrada:**<br>
Resulta que el Worlde tiene un total de 12974 palabras a entrar, pero de estas, solo 2316 pueden ser la solución. Es decir, hay palabras que puedes poner, pero que nunca serán la solución final.
Estas palabras se encuentran en los csvs valid_solutions (2316 que pueden ser solución) y valid_guesses (10658 que NO pueden ser solución) obtenidos de [kaggle](https://www.kaggle.com/datasets/bcruise/wordle-valid-words) y guardados en mi repositorio github.

**Algoritmo para encontrar la siguiente mejor palabra:**<br>
El algoritmo tiene en cuenta la frecuencia de las letras, tanto en general como por posición (frecuencia para cada una de las 5 posiciones).
Estas frecuencias las calcula en cada iteración. Es decir, una vez tengamos el primer resultado, ya tendremos varias palabras descartadas, así que solo calcularemos la frecuencia de estas posibles palabras que encajan con el resultado.<br>
Las palabras que va "ofreciendo" el algoritmo son del listado de las 12974 palabras. Pero:<br>
- Una vez el algoritmo ve que faltan 5 o menos posibles soluciones (5 de las 2316), solo ofrece palabras de estas posibles soluciones.
- Una vez quedan 2 posibles soluciones, sale del algoritmo y ofrece una de las 2:
- Una vez que queda 1 posible solución, sale del algoritmo y ofrece la solución.
