![](ia.png)

## Busquedas locales

Repositorio con código y proyectos de búsquedas locales con los algoritmos

1. Descenso de colinas
2. Temple (recocido) simulado
3. Algoritmos genéticos

En el archivo `blocales.py` vas a encontrar las clases y funciones necesarias para el desarrollo de los algoritmos de descenso de colinas y temple simulado, así como la definición genérica de un problema de búsqueda local.

Para ver como funciona, revisa el archivo `nreinas.py` y ejecútalo. Ten la libertad de probar para diferentes números de reinas, diferentes reinicios aleatorios (en el caso del descenso de colinas) o diferentes calendarizadores de temperatura para el algoritmo de temple simulado.


## Primera parte: haciendo grafos *bonitos* (50 pts.)

Una de las dificultades más importantes de plantear un problema de búsqueda local (o en general de optimización), es el problema de establecer una función de costo que realmente sea conveniente y represente lo que uno busca.

Así que vamos a revisar un problema cuyo planteamiento es bastante subjetivo, que es dibujar un *grafo* que se vea *Bonito* (o *claro*). Este problema lo podemos ver parcialmente resuelto. 

Pero como podrás observar, en los resultados, el costo propuesto no hace figuras particularmente bonitas, y esto es porque lo único que considera es el numero de cruces.

Una manera de buscar mejores resultados es incluir en el costo el ángulo entre dos aristas conectadas al mismo vértice, dandole un mayor costo si el ángulo es muy pequeño (positivo o negativo). Igualmente se puede penalizar el que dos nodos estén muy cercanos entre si en la gráfica.

Así, vamos a calcular el costo en cuatro partes, una es el numero de cruces (ya programada), otra la distancia entre nodos (ya programada) y otro el ángulo entre arista de cada nodo (esta la tienes que programar en el método `angulo_aristas`). Por último, programa un criterio propio en el método `criterio_propio`. En el método `costo`asigna valores a `K1`, `K2`, `K3` y `K4` y justifica tu criterio.

El método que genera un vecino aleatorio es muy malo y puede ser mejorado fácilmente. Por favor modifica el método `vecino_aleatorio` para que se genere un mejor vecino. Para obtener mejores resultados del temple simulado, es necesario utilizar una función de calendarización acorde con el método en que se genera el vecino aleatorio. Busca diferentes métodos de calendarización (al menos uno más) y ajusta los parámetros para que obtenga la mejor solución posible en el menor tiempo posible.

Inventate un grafo más feo y muestra como el temple simulado lo hace lucir mejor.

## Algoritmo genético (50 puntos)

En el archivo `genetico.py` se presenta una clase genérica de algoritmo genético y a partir de esa se desarrolla un algoritmo genético pensado para problemas de permutaciones, como son las *N-Reinas* o el *Problema del agente viajero*.

Modifica los parámetro del algoritmo genético (el cual se conoce como `genetico.GeneticoPermutaciones`) buscando que el algoritmo encuentre **siempre** una solución óptima, utilizando el menor tiempo posible en promedio. Realiza esto para las 8, 16, 32, 64 y 128 reinas. Lo que puedes modificar es el tamaño de la población, el número de generaciones y/o la probabilidad de mutación. Responde las siguientes preguntas:

- ¿Cuales son en cada caso los mejores valores?  
- ¿Que reglas podrías establecer para asignar valores según tu experiencia?


Tu trabajo va a ser, ahora, realizar **otro** algoritmo genético para permutaciones para lo cual, en el archivo `genetico_tarea.py` tienes que programar un algoritmo genético para permutaciones completamente diferente al que ya tenemos, en donde hay que programar los métodos:

- `__init__`
- `estado_a_cadena`
- `cadena_a_estado`
- `adaptación`
- `selección`
- `cruza_individual`
- `mutación`
- `reemplazo_generacional`

Modifica los parámetro del algoritmo genético que inventaste. De ser muchos parámetros, restríngete a 2 o 3, buscando que el algoritmo encuentre **siempre** una solución óptima, utilizando el menor tiempo posible en promedio. Realiza esto para las 8, 16, 32, 64 y 128 reinas. Responde las siguientes preguntas:

- ¿Cuales son en cada caso los mejores valores?  
- ¿Que reglas podrías establecer para asignar valores según tu experiencia?

Y con eso es todo, espero sea un buen punto de partida para entender las búsquedas locales.