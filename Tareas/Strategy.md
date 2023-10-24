# Strategy
_es un patrón de tipo comportamental (behavioral pattern), es decir, se centra en definir la forma en la que se produce el intercambio de mensajes entre distintos componentes. Básicamente, su propósito es mantener un conjunto de algoritmos (estrategias) de entre los cuales el objeto cliente puede elegir aquel que le conviene e intercambiarlo dinámicamente según sus necesidades._
### Algunos ejemplos en los que puede ser útil:
- Funcionalidad de exportar que permite elegir distintos formatos: PDF, CSV, XML, JSON…
- Manejar las opciones de visualización de un texto: alinear izquierda, centrar, alinear derecha, justificar…
- Calcular la ruta en un sistema GPS basándonos en distintos vehículos: a pie, en bici, en coche…
- Mover una pieza en juego tipo ajedrez: peón, torre, caballo, alfil, dama, rey

### Actores
_Hay 4 actores diferenciados en este patrón:_
- Cliente
 
_Es quien solicita la acción, también es quien fija la estrategia a utilizar. No forma parte del core de la lógica, solo interactúa con el contexto._

- Contexto

_Es la clase que alberga la información necesaria para ejecutar las estrategias y también la clase que hace uso de ellas. Al contexto debemos de informarle de la estrategia a utilizar mediante un setter u otro mecanismo._

- Interfaz de la estrategia

_Es el contrato que debe de cumplir cada estrategia que queramos implementar. Este contrato permite al contexto conocer y estandarizar el uso de las estrategias, no teniendo que conocer la implementación final de cada una para tener que ejecutarlas.
Hay una forma alternativa al uso de la Interfaz de la Estrategia, que es simplemente pasarle el contexto a las estrategias concretas. En ese caso obviamente no sería necesario definir una interfaz._

- Interfaz concreta
  
_Es una implementación del contrato de la interfaz, si pensamos en alguno de los casos anteriores de ejemplo, es quien define cómo se mueve un peón, quién sabe cómo se calcula una ruta en bici, quién sabe cómo formatear un texto centrado o cómo formatear un PDF a exportar._



