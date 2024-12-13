# Examen 1ª Evaluación
## Manuel Carrera Pazó
---

Explica a continación cada apartado del examen

Con cada apartado realiza un commit diferente

## **DIAGRAMA DE FLUJO**
##
![DAMAS](damas.png)

## **EJEMPLO TABLERO**
![Damas](https://img.freepik.com/vector-premium/tableros-ajedrez-sobre-damas-fondo-madera-o-juego-damas-piezas-marron-oscuro-marron-claro-ilustracion-vectorial_230920-3635.jpg)

#### Ejemplo de tablero con **fichas**
##### 1, 0, 2, 0, 1, 0, 2, 0
##### 0, 1, 0, 2, 0, 1, 0, 2
##### 1, 0, 2, 0, 1, 0, 2, 0
##### 0, 0, 0, 0, 0, 0, 0, 0
##### 0, 0, 0, 0, 0, 0, 0, 0
##### 2, 0, 1, 0, 2, 0, 1, 0
##### 0, 2, 0, 1, 0, 2, 0, 1
##### 2, 0, 1, 0, 2, 0, 1, 0

## **FUNCIONES PARA MEJORAR EL CODIGO CON SUS JAVADOCs**

1. **Inicializa un tablero de damas (8x8)** con valores predefinidos.
2. **Cuenta las fichas** de cada jugador.
3. **Muestra los resultados**, indicando quién va ganando o si hay empate.

```java
/**
 * 1. Inicializa un tablero de damas (8x8) con valores predefinidos.
 * 
 * @return Una matriz 8x8 que representa el tablero de damas.
 *         0 -> Casilla vacía.
 *         1 -> Ficha del Jugador 1.
 *         2 -> Ficha del Jugador 2.
 */
public static int[][] inicializarTablero() {
    return new int[][] {
        {1, 0, 2, 0, 1, 0, 2, 0},
        {0, 1, 0, 2, 0, 1, 0, 2},
        {1, 0, 2, 0, 1, 0, 2, 0},
        {0, 0, 0, 0, 0, 0, 0, 0},
        {0, 0, 0, 0, 0, 0, 0, 0},
        {2, 0, 1, 0, 2, 0, 1, 0},
        {0, 2, 0, 1, 0, 2, 0, 1},
        {2, 0, 1, 0, 2, 0, 1, 0}
    };
}
/**
 * 2. Cuenta las fichas de cada jugador en el tablero.
 *
 * @param tablero Matriz 8x8 que representa el tablero de damas.
 * @return Un array de enteros donde:
 *         [0] -> Número de fichas del Jugador 1.
 *         [1] -> Número de fichas del Jugador 2.
 */
public static int[] contarFichas(int[][] tablero) {
    int contadorJugador1 = 0;
    int contadorJugador2 = 0;

    // Recorrer el tablero
    for (int fila = 0; fila < tablero.length; fila++) {
        for (int columna = 0; columna < tablero[fila].length; columna++) {
            if (tablero[fila][columna] == 1) {
                contadorJugador1++;
            } else if (tablero[fila][columna] == 2) {
                contadorJugador2++;
            }
        }
    }
    return new int[] {contadorJugador1, contadorJugador2};
}
/**
 * 3. Muestra los resultados finales del juego.
 * Imprime la cantidad de fichas de cada jugador y determina quién va ganando.
 *
 * @param contadorJugador1 Número de fichas del Jugador 1.
 * @param contadorJugador2 Número de fichas del Jugador 2.
 */
public static void mostrarResultado(int contadorJugador1, int contadorJugador2) {
    System.out.println("Fichas Jugador 1: " + contadorJugador1);
    System.out.println("Fichas Jugador 2: " + contadorJugador2);

    if (contadorJugador1 > contadorJugador2) {
        System.out.println("Jugador 1 va ganando.");
    } else if (contadorJugador2 > contadorJugador1) {
        System.out.println("Jugador 2 va ganando.");
    } else {
        System.out.println("Empate.");
    }
}
