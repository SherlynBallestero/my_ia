# Tarea CP1.

1- Implementar una heurística para su problema que les permita mejorar la cantidad de pasos en el que llegan a la solución partiendo todos de UCS(Búsqueda de costo uniforme).

*Recuerden que heurística en este primer acercamiento no es más que una función que incorpora cierta información del problema en concreto a la manera en que se seleccionan los vecinos.

¿Que pasa si aumenta las dimensiones del tablero y si se incorporan más casillas en blanco? 

-Hagan el programa que sea lo más genérico posible para resolver el N-Puzzle independientemente de la cantidad de casillas en blanco y de las dimensiones.

*Extra CP1:
Demostrar para qué casos de configuraciones inciales, el problema N-puzzle no tiene solución factible para transformar el estado inicial en el estado objetivo
# Respuesta :
## Implementación
Para la implementación se ha empleado A* y como heurística se han empleado combinadas manhattan y la cantidad
de conflictos (piezas fuera de lugar con respecto al estado objetivo), se hizo de forma tal que no importa ni las dimensiones del tablero o la cantidad de blancos que se inserten y se verifica que el n-puzzle tenga solución factible para transformar el estado inicial en el estado objetivo a partir de las siguientes reglas:
Si N es impar, entonces la instancia del rompecabezas se puede resolver si el número de inversiones es par en el estado de entrada.
Si N es par, la instancia del rompecabezas se puede resolver si 
El espacio en blanco está en una fila par contando desde abajo (penúltimo, penúltimo, etc.) y el número de inversiones es impar.
El espacio en blanco está en una fila impar contando desde abajo (última, antepenúltima, quintaúltima, etc.) y el número de inversiones es par.
Para todos los demás casos, la instancia del rompecabezas no se puede resolver
El problema da como resultado -1 si cuando se quequean las mencionadas reglas, este no se puede resolver en caso contrario se imprime el tablero al que se llego, que siempre debe coincidir con el tablero objetivo.

### Demostrando porque estas reglas garantizan soluciones al puzzle:
Estas reglas se aplican teniendo en cuenta que:

1-si se aplican movimientos legales en un tablero de n*n con n impar se preserva la paridad del la cantidad de inversiones pues:

Mover un mosaico a lo largo de la fila (izquierda o derecha) no cambia el número de inversiones y, por lo tanto, no cambia su polaridad.
Mover un mosaico a lo largo de la columna (hacia arriba o hacia abajo) puede cambiar el número de inversiones. La ficha se mueve más allá de un número par de otras fichas (N – 1). Por lo tanto, mover aumenta o disminuye el recuento de inversión en 2 o mantiene el mismo recuento de inversión.

2- Para una cuadrícula de ancho par, lo siguiente es invariante: (#inversions par) == (en blanco en la fila impar desde abajo).Pues:

Mover un mosaico a lo largo de la fila (izquierda o derecha) no cambia el número de inversiones y no cambia la fila del espacio en blanco.
Mover un mosaico a lo largo de la columna (hacia arriba o hacia abajo) cambia el número de inversiones. La ficha se mueve más allá de un número impar de otras fichas (N – 1). Por lo tanto, el número de inversiones cambia en un número impar de veces. La fila del espacio en blanco también cambia, de impar a par, o de par a impar. Por lo tanto, ambas mitades del invariante cambian. Por lo tanto, su valor se conserva.

Combinando=> 1 + 2 = 3:  
 

Si el ancho es impar, entonces cada estado solucionable tiene un número par de inversiones.
Si el ancho es par, entonces cada estado solucionable tiene
un número par de inversiones si el espacio en blanco está en una fila con números impares contando desde abajo;
un número impar de inversiones si el espacio en blanco está en una fila numerada par contando desde abajo.


Prueba de 3: 
 

El estado inicial (resuelto) tiene esas propiedades.
Esas propiedades se preservan con cada movimiento legal.
Se puede llegar a cualquier estado solucionable desde el estado inicial mediante alguna secuencia de movimientos legales.