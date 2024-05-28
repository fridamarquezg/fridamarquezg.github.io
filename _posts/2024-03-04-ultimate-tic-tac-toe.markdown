---
layout: post
title: Ultimate Tic Tac Toe
date: 2024-03-04 00:00:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: uttt.jpg # Add image post (optional)
tags: [Programming, Learn] # add tag
---
Primer proyecto para la materia de Inteligencia Artificial.
Lo hice junto con mis amigos: Majo Velázquez (https://github.com/Majo2103) y Gerardo Guerrero (https://github.com/mellamanelpoeta) y Pablo Alazraki (https://github.com/Palazrak)

Ultimate Tic Tac Toe es una variante avanzada del clásico juego de Tic Tac Toe que introduce un nivel adicional de estrategia y complejidad. 

### Estructura del Juego
* Tablero Principal: El tablero está compuesto por nueve tableros de Tic Tac Toe más pequeños, formando una cuadrícula de 3x3.

* Sub - Tableros: Cada uno de los nueve tableros pequeños también es un juego de Tic Tac Toe por sí mismo.

### Reglas Básicas
* Movimiento Inicial: El primer jugador puede colocar su marca (X o O) en cualquier celda de cualquier tablero pequeño.

* Movimientos Subsiguientes: La ubicación de la marca de un jugador determina en qué tablero pequeño el siguiente jugador debe jugar. Por ejemplo, si el primer jugador coloca su marca en la celda central de un tablero pequeño, el próximo jugador debe jugar en el tablero pequeño central del tablero principal.

* Ganar Sub- Tableros: Los jugadores ganan un tablero pequeño siguiendo las reglas tradicionales de Tic Tac Toe (alineando tres de sus marcas en fila, columna o diagonal).

* Ganar el Juego: El objetivo es ganar tres tableros pequeños en línea en el tablero principal (horizontalmente, verticalmente o diagonalmente).

### Consideraciones Estratégicas
* Forzar Jugadas: Un jugador puede forzar al oponente a jugar en un tablero pequeño específico, lo que puede limitar las opciones del oponente y crear oportunidades estratégicas.

* Bloqueo y Control: Controlar los tableros pequeños clave es crucial, especialmente aquellos que podrían influir en múltiples direcciones de victoria en el tablero principal.

Ultimate Tic Tac Toe añade una dimensión estratégica adicional al juego clásico, haciendo que los jugadores deban pensar varios movimientos por adelantado y considerar tanto las jugadas inmediatas como sus impactos futuros.

### Implementación del algoritmo Minimax
El algoritmo Minimax es una técnica de toma de decisiones utilizada en teoría de juegos e inteligencia artificial, particularmente en juegos de suma cero como el ajedrez y el Tic Tac Toe. Este algoritmo busca minimizar la posible pérdida máxima en una situación adversa. En un juego de dos jugadores, el algoritmo alterna entre simular movimientos del jugador "maximizador" que intenta maximizar su puntuación y movimientos del jugador "minimizador" que intenta minimizar la puntuación del maximizador. Minimax examina todas las posibles jugadas, evalúa los estados resultantes del tablero, y elige la jugada que conduce al mejor resultado posible para el jugador en turno, asumiendo que el oponente también jugará óptimamente. Esta estrategia permite a los jugadores tomar decisiones óptimas basadas en un análisis profundo de las posibles consecuencias de cada jugada.

### Funcion heurística
En el algoritmo Minimax, una función heurística desempeña un papel crucial cuando se trata de juegos o problemas donde la profundidad completa del árbol de decisión no es practicable debido a la complejidad y la cantidad de posibles movimientos. Aquí te explico su función en detalle:

Evaluación de Estados Intermedios: 
* En situaciones complejas, como en juegos con muchos movimientos posibles y profundas ramas de decisiones (como el ajedrez), es impráctico evaluar todas las posibles secuencias hasta los estados finales del juego.

* Una función heurística permite evaluar los estados intermedios del juego cuando el algoritmo debe detenerse antes de alcanzar el final del juego debido a limitaciones de tiempo o recursos computacionales.

Asignación de Valores de Utilidad:
* La función heurística asigna un valor numérico a un estado del juego, indicando cuán favorable es ese estado para el jugador maximizador.

* Estos valores se utilizan para comparar y decidir entre diferentes movimientos, guiando el algoritmo hacia las jugadas más prometedoras sin necesidad de completar todo el árbol de decisión.

Optimización del Rendimiento:
* Emplear una función heurística permite al algoritmo Minimax hacer estimaciones razonables sobre el valor de un estado del juego basado en características observables, como la posición de las piezas en un tablero, el control del centro en ajedrez, o la proximidad a la victoria en Tic Tac Toe.

* Esto mejora el rendimiento y la eficiencia del algoritmo, permitiendo tomar decisiones más rápidas y efectivas dentro de las limitaciones computacionales.

Para nuestro proyecto, decidimos crear una función heurística que tiene la siguiente forma:
![T1]({{site.baseurl}}/assets/img/t1.png)

### Función 1: Lineas ganadoras en los sub-tableros
![T2]({{site.baseurl}}/assets/img/t2.png)
### Función 2: Lineas ganadoras en el tablero
![T3]({{site.baseurl}}/assets/img/t3.png)
### Función 3: Valor de cada posición en el tablero
![T4]({{site.baseurl}}/assets/img/t4.png)
![T4]({{site.baseurl}}/assets/img/t5.png)