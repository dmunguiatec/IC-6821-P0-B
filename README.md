IC-6821 Diseño de Software  
Prof. Diego Munguia Molina  
TEC IC-AL
---
# Proyecto 1

## Objetivos de aprendizaje

1. Explicar las mejores prácticas de nomenclatura en código limpio. (II)
2. Diseñar código partiendo de los principios de programación orientada a objetos (VI)

## Descripción

Este proyecto consiste en implementar el juego 2048 en Java, aplicando los principios de programación orientada a objetos y las buenas prácticas de diseño de software.

2048 es un juego de un solo jugador en el que el jugador desplaza mosaicos con valores numéricos en un tablero cuadrado (4x4 en la versión clásica). Puede utilizar esta versión del juego como referencia https://es.2048.org/.

Cuando dos mosaicos con el mismo valor colisionan, se combinan en un solo mosaico con el valor sumado. El objetivo es alcanzar el mosaico con el valor 2048 (o la mayor puntuación posible antes de que no queden movimientos).




### Requerimientos

* El tablero es una cuadrícula de `4 x 4`, en el futuro podría modificarse para que tenga dimensiones configurables `n x n`.
* Se inicializa con dos mosaicos de valor `2` o `4` colocados en posiciones aleatorias.
* Cada turno aparece un nuevo mosaico (`2` o `4`) en una posición vacía.
* La probabilidad de que un mosaico sea `2` o `4` debería fácilmente modificable en el código. Inicialmente se puede establecer como 60% para el `2` y 40% para el `4`. 
* El jugador puede mover todos los mosaicos en cuatro direcciones: arriba, abajo, izquierda, derecha. 
* Mosaicos con el mismo valor que colisionan se combinan para producir un mosaico cuyo valor es la suma de los dos mosaicos originales.
* Cada vez que hay una colisión el puntaje del jugador incrementa en el valor de la suma de los mosaicos.
* Cuando hay un movimiento en cualquier dirección se mueven los mosaicos al último espacio disponible en dicha dirección. Si ningún mosaico se puede mover porque no hay espacios disponibles entonces entendemos que el movimiento en esa dirección no es válido.
* Condición de derrota: cuando no hay movimientos válidos en ninguna dirección.
* Condición de victoria: cuando aparece un mosaico con valor `2048`.
* El juego se implementará en consola. El diseño debe considerar la posibilidad de implementar una interfaz de usuario gráfica en el futuro.
* Al inicio del juego, y después de cada movimiento, se imprime el estado actual del tablero en pantalla en texto plano.
```
+----+----+----+----+
|  2 |    |  2 |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
Puntaje: 0

+----+----+----+----+
|  4 |    |    |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
Puntaje: 4

```
* Los movimientos se aplicarán con las teclas `W` (arriba), `S` (abajo), `A` (izquierda), `D` (derecha).
* Los movimientos se aplican inmediatamente, no requieren de `Enter` y no se imprime el caracter correspondiente en pantalla.
* Los tres puntajes más altos se guardan en un archivo y siempre se imprimen en pantalla al iniciar el juego.

```
Récord
RDJ 7368
HWK 6528
DBN 6200

+----+----+----+----+
|  2 |    |  2 |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
|    |    |    |    |
+----+----+----+----+
Puntaje: 0

```
* Al finalizar el juego por condición de victoria o de derrota se verifica si el puntaje actual mejora alguno de los tres mejores puntajes y de ser así se registra, solicitando al jugador sus iniciales (3 letras, siempre mayúsculas).
* Al finalizar el juego por condición de victoria o de derrota se termina la ejecución del programa.
* La tecla `Q` se usa para salir de un juego no finalizado, antes de salir se guarda el estado actual del juego en un archivo, la próxima vez que ingrese al juego se restaura.
* 

## Metodología

* El proyecto se trabajará en equipos de 1, 2 o 3 personas.
* El proyecto se desarrollará en el transcurso de tres semanas.
* El proyecto se desarrollará en Java siguiendo el paradigma de programación orientada a objetos.
* La entrega del proyecto será a través del repositorio git facilitado por la persona docente.
* El proyecto será evaluado a través de una rúbrica de evaluación global (50%) y a través de una prueba escrita individual aplicada a todas las personas miembros del equipo (50%).

## Rúbricas de evaluación

Disponible en el siguiente enlace:

https://docs.google.com/spreadsheets/d/1F0WUaI4iwoMKwNI7vRiV-Us63DX5jJXdH71UO2cZkoc

## Ambiente de desarrollo

Ejecutar pruebas y reporte de cobertura

```bash
./gradlew clean test jacocoTestReport
```

Ejecutar checkstyle

```bash
./gradlew clean check
```
