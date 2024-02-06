# Clases Prácticas de IA
## Integrantes

Sherlyn Ballestero cruz

Maria de Lourdes Choy

Alejandro Yero Valdés


## Tarea CP2. Se entrega el lunes. Tarea por equipos de a 3.

1- Implementar los métodos en el Notebook de Jupyter de la CP relacionados con el problema de los Pancakes. 

2- Ejecutar y resolver instancias del problema con al menos 3 de los algoritmos de búsqueda implementados en la CP. Entre los algoritmos utilizados debe estar A* con la heurística dada en clases para el problema.

3- Demuestre la admisibilidad y consistencia de dicha heurística si lo fuera en cada caso.

4- Ejecutar las celdas relacionadas con el rendimiento de los algoritmos al final de la CP. También, diseñe e implemente otra heurística respecto al problema y compare con los métodos correspondientes también al final de la CP con respecto a la heurística anterior.
## respuesta 3
### Admisibilidad y Consistencia de la Heurística del Gap

### Admisibilidad

La heurística del "Gap" es admisible porque nunca sobreestima el costo real para llegar al objetivo. Si consideramos un estado n y su sucesor n' donde se ha realizado un movimiento válido, la heurística del "Gap" siempre subestima el costo real, ya que el número de casillas desordenadas no aumenta después de un movimiento válido.

### Consistencia

La heurística del "Gap" es consistente porque satisface la propiedad triangular. Para dos nodos adyacentes n y m, donde n es un estado antes de realizar un movimiento y m es el estado después de ese movimiento, tenemos:

h(n) <= c(n, m) + h(m)

Donde c(n, m) es el costo de realizar el movimiento de n a m. Si eliminamos una ficha del tablero, el costo de llegar al objetivo aumenta, lo que refleja la relación triangular y mantiene la consistencia de la heurística.

