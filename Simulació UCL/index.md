# Simulació UCL

<div class="tabs">
  <ul>
    <li><a href="../">Inicio</a></li>
    <li><a href="/Strava/">Strava Project</a></li>
    <li><a href="/Simulació UCL/">Simulació UCL</a></li>
    <li><a href="/Flags_Similarity/">Flags Similarity</a></li>
    <li><a href="/Wordle_Solver/">Wordle</a></li>
    <li><a href="/Puzzle_Solver/">Puzzle</a></li>
  </ul>
</div>
<link rel="stylesheet" href="/custom.css"><br>

**Publicación**: 30/08/2025<br>
--> **Link Repositorio Github** ([https://github.com/arnaugr55/Strava_project](https://github.com/arnaugr55/Simulacio_UCL))<br>

Proyecto Python que simula el desarrollo de la Champions League. Desde la definición de los 144 partidos de la Fase Liga hasta la final.


***Código***<br>
1. **main.py**: Código que se ejecuta y que orquesta todo el flujo. Va llamando a las funciones de funcions.py en orden y les va entrando los parámetros y variables que toquen según lo que indique el usuario. Como digo, al ejecutarlo se le harán unas pocas preguntas por pantalla al usuario que este debe responder. Son preguntas del estilo: *¿cuántas iteraciones quieres?, quieres coger una fase liga ya generada?...*
2. **funcions.py**: Es donde está todo el grueso. Está compuesta por funciones, cada una con un propósito distinto. (ej: hacer la fase liga, simular partidos, generar el html de la clasificación...)

Los scripts se encuentran en el github del proyecto. Ahí están comentados paso a paso.

<br>***Desarrollo de una UCL***<br>

Generación de la Fase Liga:
1. **validem_sorteig_fase_lliga()**: Llama a *sorteig_fase_lliga()* hasta que esta función le devuelva una fase liga completa. Tras esto, se guarda la fase de liga como *enfrontaments_matriu_AAAAAAAAAA*. Donde AAAAAAAAAA son 10 cifras o letras aleatorias.
2. **sorteig_fase_lliga()**: Itera equipo a equipo y le va metiendo los 8 rivales. Los va guardando en una matriz 36x36. En cuanto ve que a un equipo no le puede meter más rivales (ya sea por +2 rivales misma liga o +2 rivales mismo bombo), sale de la función, por mucho que la fase liga esté incompleta. Aun así, como *validem_sorteig_fase_lliga()* verá que no está completa, la volverá a llamar empezando de nuevo... y así hasta que se consigan los 144 enfrentamientos.
3. **definim_local_visitant()**: Convierte la matriz de partidos en pandas dataset con los 144 partidos. Luego para cada equipo, le da 4 partidos como local y 4 como visitante. Tras esto, ordena los partido para meter delante al equipo local (ej: PSV vs PSG, el local será el PSV)
4. **fase_lliga_imatge()**: Se muestran 4 imágenes. Cada una de ellas son los 9 equipos de cada bombo, con sus 8 respectivos rivales.
5. **assignar_jornades()**: Añade, para cada partido, la jornada en la que se jugará (de 1 a 8).
---> Las funciones 1, 2, 3 y 5 suelen tardar bastante, por lo que tenemos la posibilidad de coger una fase liga ya pre generada, evitando así, que se llame a estas funciones.
   
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Simulació UCL/resources/fase_lliga_POT1.png" alt="Se muestra la fase liga" width="400">
</div><br/>


Simulación de la Fase Liga:
1. **fase_lliga()**: Función que simula la fase liga. Va iterando jornada a jornada, simulando los partidos y actualizando la clasificación.
2. **partit()**: Función que simula 1 partido y da una victoria local, una victoria visitante o un empate. *Como esta es la parte, quizás más interesante del código, os muestro cómo se simula un partido y cómo van las probabilidades.*
     -  Los 36 equipos tienen unos "puntos de poder asociados". Estos puntos de poder son en la nota del equipo FC25.
       - Entonces, como va, por ejemplo, si se enfrentan PSG (83 puntos de poder) y Benfica (79 puntos de poder)
          1. Se tiene en cuenta el efecto campo. Al local se le suma +2 y al visitante -1. (PSG --> 85 y Benfica --> 78)
		  2. Usamos la fórmula puntos_poder_1^elevat / (puntos_poder_1^elevat + puntos_poder_2^elevat) para calcular los porcentajes. "elevat" depende de la ronda, en la fase liga elevat = 15. 85^15 / (85^15 + 78^15) = 78% --> PSG y 22% --> Benfica
		  3. A esta fórmula le falta el empate. Cuanto mayor es la diferencia entre los equipos, menor es la probabilidad de empate. En este caso, al estar entre un rango de 20% a 30%, la probabilidad de empate será del 0.14. Entonces (PSG --> 67.1%, Benfica --> 18.9%, empate --> 14%)
		  4. Simulamos el partido usando estos porcentajes calculados.
	- También hay variables que se tienen en cuenta, como que el Bodo/Glimt en local tiene más ventaja, o que los equipos ya clasificados en la 7a jornada, jugarán la 8a con suplentes (por lo que se les bajan sus puntos de poder)... Estos están explicados en el código.
4. **html_results_fase_lliga()**: Crea y muestra un HTML con los resultados de los 18 partidos de cada jornada. Se llama también en los playoffs, para ver que equipos pasan a octavos.
5. **html_table_fase_lliga()**: Crea y muestra un HTML con la clasificación de la fase liga tras cada jornada. Muestra las zonas de clasificación directa, playoffs y eliminación en colores distintos.
6. **desempat()**: Se encarga de, cuando han finalizado las 8 jornadas, desempatar a los equipos que tienen los mismos puntos.

<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Simulació UCL/resources/resultats_jornada.png" alt="Se muestran los resultados de la jornada." width="700">
</div><br/>
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Simulació UCL/resources/classificacio_final.png" alt="Se muestra la clasificación en la fase liga" width="400">
</div><br/>


Playoffs y rondas eliminatorias:
1. **determinar_classificat()**: Llama 2 veces a *partit()*, simulando la ida y la vuelta de la eliminatoria. Si tras los 2 partidos los equipos quedan empatados, se llama a *desempat()*. Retorna el quipo que pasa la eliminatoria.
2. **update_results()**: Actualiza el diccionario "arribat" que va guardando a qué ronda llega cada equipo.
3. **genera_imatge_brackets_final()**: Va generando el bracket de octavos hasta la final. A cada clic, la imagen "avanza" simulándose un partido.
4. **bracket_phase()**: Simula las rondas eliminatorias, llamando a *determinar_classificat()* para los partidos hasta llegar a la final, que llama a *partit()*.

<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Simulació UCL/resources/resultats_playoffs.png" alt="Se muestran los resultados de los playoffs." width="700">
</div><br/>
<div style="text-align: center;">
  <img src="https://arnaugr55.github.io/Simulació UCL/resources/bracket_final.png" alt="Se muestra el bracket" width="800">
</div><br/>


***CSV con las simulaciones***<br>
Tenemos la opción de hacer varias iteraciones y guardar los resultados de todos ellos en un csv. En este, se muestra, para cada uno de los 36 equipos, cuantas veces han ganado la Champions o han llegado a la final, o semi...<br>
Este de aquí abajo es un ejemplo con 10.000 iteraciones para la UCL de la temporada 2025/26.
<iframe src="https://arnaugr55.github.io/Simulació_UCL/resources/Equips_resultats_10000x.html" width="100%" height="500px"></iframe>
