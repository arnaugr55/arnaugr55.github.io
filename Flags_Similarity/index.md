# Strava Dashboard Project

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

<br>***Ejemplo del dataset***<br>
Algunas de las filas del dataset:
| name           | landmass | zone | area | population | language | religion | bars | stripes | colours | red | green | blue | gold | white | black | orange | mainhue | circles | crosses | saltires | quarters | sunstars | crescent | triangle | icon | animate | text | topleft | botright |
|----------------|----------|------|------|------------|----------|----------|------|---------|---------|-----|-------|------|------|-------|-------|--------|---------|---------|---------|----------|----------|----------|----------|----------|------|---------|------|---------|----------|
| Afghanistan    | 5        | 1    | 648  | 16         | 10       | 2        | 3    | 0       | 4       | 1   | 1     | 0    | 0    | 1     | 1     | 0      | black   | 0       | 0       | 0        | 0        | 0        | 0        | 1        | 0    | 1       | black | green   |
| Albania        | 3        | 1    | 29   | 3          | 6        | 6        | 0    | 0       | 3       | 1   | 0     | 0    | 1    | 0     | 1     | 0      | red     | 0       | 0       | 0        | 1        | 0        | 0        | 0        | 1    | 0       | red   | red     |
| Algeria        | 4        | 1    | 2388 | 20         | 8        | 2        | 2    | 0       | 3       | 1   | 1     | 0    | 0    | 1     | 0     | 0      | green   | 0       | 0       | 0        | 1        | 1        | 0        | 0        | 0    | 0       | green | white   |
| American-Samoa | 6        | 3    | 0    | 0          | 1        | 1        | 0    | 0       | 5       | 1   | 0     | 1    | 1    | 1     | 0     | 1      | blue    | 0       | 0       | 0        | 0        | 0        | 1        | 1        | 1    | 0       | blue  | red     |
| Andorra        | 3        | 1    | 0    | 0          | 6        | 0        | 3    | 0       | 3       | 1   | 0     | 1    | 1    | 0     | 0     | 0      | gold    | 0       | 0       | 0        | 0        | 0        | 0        | 0        | 0    | 0       | blue  | red     |
| Angola         | 4        | 2    | 1247 | 7          | 10       | 5        | 0    | 2       | 3       | 1   | 0     | 0    | 1    | 0     | 1     | 0      | red     | 0       | 0       | 0        | 1        | 0        | 0        | 1        | 0    | 0       | red   | black   |
| Anguilla       | 1        | 4    | 0    | 0          | 1        | 1        | 0    | 0       | 4       | 1   | 0     | 1    | 1    | 1     | 0     | 0      | blue    | 0       | 2       | 1        | 1        | 0        | 0        | 0        | 1    | 0       | white | blue    |
| Antigua-Barbuda| 1        | 4    | 0    | 0          | 1        | 1        | 0    | 1       | 5       | 1   | 0     | 1    | 1    | 1     | 1     | 0      | red     | 0       | 0       | 0        | 1        | 0        | 1        | 0        | 0    | 0       | black | red     |
| Argentina      | 2        | 3    | 2777 | 45         | 2        | 0        | 0    | 3       | 2       | 0   | 0     | 1    | 0    | 1     | 0     | 0      | blue    | 0       | 0       | 0        | 0        | 0        | 0        | 0        | 0    | 0       | blue  | blue    |

<br>

<br>***Resultados***<br>
--TOP10 Similitudes--<br>
xxx
--Grafos Generados--<br>
Se han generado un total de 6 grafos. Esos son los siguientes.
Además, en el notebook también podemos ver que se han hecho análisis (xxxx) sobre los resultados. 


