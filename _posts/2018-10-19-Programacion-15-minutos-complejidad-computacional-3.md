---
published: true
title: Programación en 15 minutos - Complejidad Computacional (Parte 3)
layout: post
license: ccbysa
tsocurl: http://thescienceofcode.azurewebsites.net/Articles/Show/5b4575cf407d6f33cc0e9d88
---
![Programación en 15 minutos - Complejidad Computacional 3]({{ site.baseurl }}/images/complexity-3.jpg)

{:.img-footer}
[Photo under Public Domain](https://unsplash.com/photos/E0AHdsENmDg){:target='_blank'}

En este capítulo exploraremos las diferentes funciones de crecimiento que probablemente vayamos a encontrarnos en nuestra carrera como programadores.

<!--more-->

# Órdenes de crecimiento más comunes

Si bien la **Notación Big O** puede utilizarse con cualquier función matemática, como programadores lo más común es encontrarse con alguna de las siguientes funciones:

## Crecimiento constante

> Cuando un algoritmo puede dar la respuesta utilizando la misma cantidad de pasos, independiente del tamaño de la entrada **n**, decimos que tiene una complejidad constante, que está representada por **O(1)**

En general, son problemas solucionables mediante una única instrucción o mediante operaciones matemáticas. Por ejemplo:

* Calcular la sumatoria de los primeros **n** enteros usando la fórmula **n (n + 1) / 2**.

* Encontrar el elemento en una posición **x** de un vector **v** (Sería simplemente acceder **v[x]**, lo que se consigue con vector en tiempo constante -en otras estructuras de datos como los mapas este tiempo puede variar).

* Este problema de Code Forces [Theatre Square](https://codeforces.com/problemset/problem/1/A){:target='_blank'}

Este tipo de soluciones son deseables ya que en términos generales podemos decir que son **algoritmos óptimos**, que escalan bien con el tamaño de la entrada y que normalmente tienen muy buen desempeño (son muy rápidos).

## Crecimiento logarítmico

<center>

| ![Binaria](https://theproductiveprogrammer.blog/013/binary-search.png) |
| :--: |
| *Imagen de [Top Coder](https://www.topcoder.com/blog/binary-stride-a-variant-on-binary-search/){:target='_blank'}. Usada sólo con fines educativos.*  |

</center>

> Cuando un algoritmo en cada iteración descarta la mitad, un tercio o en general una fraccion de las posibles soluciones, decimos que tiene una complejidad logarítmica, que está representada por **O(log_b(n))**.

* **log(n)**: si no se especifica la base, los programadores consideramos que la base del logarítmo es 2, lo que quiere decir que en cada paso se descarta la mitad de las posibilidades. 

  * En general recorridos en árboles binarios.

  * La solución más popular de este tipo es la **búsqueda binaria**, que puede usarse por ejemplo, en este problema de Code Forces: [Worms](https://codeforces.com/contest/474/problem/B){:target='_blank'}.

* Funciones de crecimiento con logarítmos de otras bases, si bien existen, no son muy comunes de encontrar en programación.

Este tipo de soluciones también escalan correctamente y por lo general tienen muy buen desempeño.

## Funciones de crecimiento lineal

> Cuando un algoritmo  itera una cantidad constante de veces sobre una entrada de tamaño **n** para obtener la respuesta, decimos que tiene una complejidad lineal, que está representada por **O(n^c)**

Este tipo de funciones aparecen cuando tenemos que iterar 1, 2 o en general, una cantidad constante de veces sobre los datos para encontrar la respuesta.

* **O(n)**: Cuando iteramos una única vez sobre la entrada.
  
  * Búsqueda lineal.

  * Hallar el mayor elemento de un vector.

  * Hallar la sumatoria de los primeros **n** enteros sumando *1 + 2 + 3 ... n* dentro de un ciclo.

  * Este problema de Code Forces [Police Recruits](https://codeforces.com/contest/427/problem/A){:target='_blank'}  


* **O(n²)**: Se da cuando tenemos que realizar aproximadamente n² operaciones. Por ejemplo,

<center>

  | ![Bubble sort](https://upload.wikimedia.org/wikipedia/commons/archive/5/54/20140912160203%21Sorting_bubblesort_anim.gif) |
  | :--: | 
  | *Bubble Sort [Wikipedia CC-BY-SA](https://commons.wikimedia.org/wiki/File:Sorting_bubblesort_anim.gif){:target='_blank'}* |
 
 </center>

    
  
    
    * Organizar un vector usando bubble sort, ya que debemos recorrer todos los elementos y comparar cada uno de ellos con el resto de elementos (**n x n = n²**) .

    * En general, operaciones con matrices.

    * Este problema de Code Forces [Toy Cars](https://codeforces.com/contest/545/problem/A)

Este tipo de soluciones funcionan muy bien en aplicaciones de tiempo real (como los videojuegos), siempre y cuando el tamaño de la entrada no sea exageradamente grande (cientos de miles máximo). De igual forma, en otro tipo de aplicaciones, cuando los datos llegan a *millones*, el desempeño del algoritmo se ve afectado.


## Crecimiento pseudo-logarítmico

> Cuando un algoritmo realiza **n** veces un procediento de tiempo **logarítmico** obtener la respuesta, decimos que tiene una complejidad pseudo-logarítmica, que está representada por **O(nlog(n))**

<center>

| ![Quicksort](https://upload.wikimedia.org/wikipedia/commons/6/6a/Sorting_quicksort_anim.gif) |
| :--: |
| *Quick sort [Wikipedia CC-BY-SA](https://en.wikipedia.org/wiki/Quicksort#/media/File:Sorting_quicksort_anim.gif){:target='_blank'}* |

</center>

* Merge Sort

* Heap Sort

* Quick Sort

* En el problema [Worms](https://codeforces.com/contest/474/problem/B){:target='_blank'}, si tenemos en cuenta **toda** la entrada, estamos realizando **n** búsquedas binarias, una por cada caso de prueba. 

Este tipo de soluciones tiene un comportamiento relativamente similar al de la categoria directamente anterior.

## Crecimiento exponencial

> Cuando un algoritmo realiza **2^n**, **3^n** o en general **C^n** pasos para obtener la respuesta, decimos que tiene una complejidad exponencial, que está representada por **O(C^n)**

Por lo general esto se produce cuando en cada paso, en vez de reducirse la cantidad de respuestas posibles, se van duplicando, triplicando... es decir, lo contrario a una solución logarítmica. 

<center>

| ![Brute force](https://upload.wikimedia.org/wikipedia/commons/2/2b/Bruteforce.gif) |
| :--: |
| Ejemplo de una fuerza bruta contra un algoritmo mejor optimizado. [Wikipedia CC-BY-SA](https://es.m.wikipedia.org/wiki/Archivo:Bruteforce.gif) |

</center>

* Algoritmos de fuerza bruta, es decir, en los que se prueban todos los posibles caminos para ver cuál de ellos lleva a la respuesta correcta.

* Este problema de Code Forces: [Shower Line](https://codeforces.com/contest/431/problem/B){:target='_blank'}


Este tipo de respuestas son fáciles de encontrar y de programar, pero tienen graves problemas de desempeño ya que la cantidad de pasos con respecto al tamaño de la entrada escala muy rápidamente.

## Comentarios finales de este capítulo

Cuando abrimos los problemas de **Code Forces**, podemos ver que en cada uno de ellos el tamaño de la entrada está especificado, esto le permite a programadores bien entrenados, determinar a priori que tipo de algoritmos usar. Por ejemplo para Shower Line, el problema de fuerza bruta, la entrada máxima es una fila de 5 personas mientras que para el problema de tiempo constante la entrada máxima es de 1.000'000.000.

Por otro lado, cuando hablamos de programa reales los límites son aún más difusos, sin embargo todo lo que hemos aprendido es una guía que bien utilizada, puede ayudarnos a tomar mejores decisiones cuando estemos programando.

> **Pro tip:** se debería practicar los problemas sugeridos, pasar de largo por todos estos conceptos no es suficiente para interiorizalos. Al pricipio pueden parecer difíciles y quizá en ocasiones sea necesario recurrir a las soluciones de otros, pero estudiarlas a conciencia e intentar llegar a respuestas propias, es la mejor forma de mejorar como programadores.

En el próximo capítulo veremos cómo determinar la complejidad de un algoritmo nada más dando un vistazo al código fuente.

¡Hasta la próxima!
