# Investigación
## Commit
_Los commits son la base principal del trabajo de Git, ya que es el comando más usado para guardar cualquier cambio en esta herramienta. Si te preguntas qué es un commit y como agregar un commit en git, te puedes hacer una idea al entenderlo como una captura de pantalla del trabajo que haces cada segundo en Git, allí se crea una versión del proyecto en lo que sería el repositorio local.._
### Caracteristicas
_Los commits tienen dos características muy importantes las cuales sirven para comprender mejor su funcionamiento._
- Como usuario, puedes recordar los cambios que fueron aplicados en cualquier versión con fechas anteriores, incluso logrando revertir el progreso del proyecto a esa última versión.
- Si se editan varios commits en diferentes partes del proyecto, estos cambios no se sobrescribirán entre sí, aunque los autores no tengan conexión alguna. Esto da peso en la balanza a favor de Git en comparación con otras herramientas.

### Comandos
_Para genera un commit_

    $ git commit -a -m 'mensaje o identificador de commit'


## Rama
_Una rama Git es simplemente un apuntador móvil apuntando a una de esas confirmaciones. La rama por defecto de Git es la rama master. Con la primera confirmación de cambios que realicemos, se creará esta rama principal master apuntando a dicha confirmación. En cada confirmación de cambios que realicemos, la rama irá avanzando automáticamente._
### Comandos 
_Para crear una rama:_
 
    $ git branch nomRama

_Cambiar de rama_

    $ git checkout nomRama

## Merge
_La fusión es la forma que tiene Git de volver a unir un historial bifurcado. El comando git merge permite tomar las líneas independientes de desarrollo creadas por git branch e integrarlas en una sola rama._

### Funcionamiento
_git merge combinará varias secuencias de confirmaciones en un historial unificado. En los casos de uso más frecuentes, git merge se utiliza para combinar dos ramas. Los ejemplos siguientes del presente documento se centrarán en este patrón de fusión de ramas. En estos casos, git merge toma dos punteros de confirmación, normalmente los extremos de la rama, y encuentra una confirmación base común entre ellos. Una vez que Git encuentra una confirmación base en común, crea una "confirmación de fusión" nueva que combina los cambios de cada secuencia de confirmación de fusión puesta en cola._

### Codigo 
_Primero debes de estar en la rama master_

    $ git checkout master

_Cuando estes en la rama master deberas de hacer el merge de la rama con la que quieres hacer el merge_

    $ git merge nomRama

## Rebase
_Es el proceso de mover o combinar una secuencia de confirmaciones a una nueva confirmación base. El cambio de base es más útil y se visualiza más fácilmente en el contexto de un flujo de trabajo de ramificación de funciones. El proceso general se puede visualizar de la siguiente manera:_

