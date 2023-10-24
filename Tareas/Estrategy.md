# 3 PATRONES
## Singleton
_Es un patrón de diseño creacional que nos permite asegurarnos de que una clase tenga una única instancia, a la vez que proporciona un punto de acceso global a dicha instancia._
### Pseudocódigo
_En este ejemplo, la clase de conexión de la base de datos actúa como Singleton. Esta clase no tiene un constructor público, por lo que la única manera de obtener su objeto es invocando el método obtenerInstancia. Este método almacena en caché el primer objeto creado y lo devuelve en todas las llamadas siguientes._
      // La clase Base de datos define el método `obtenerInstancia`
      // que permite a los clientes acceder a la misma instancia de
      // una conexión de la base de datos a través del programa.
    class Database is
    // El campo para almacenar la instancia singleton debe
    // declararse estático.
    private static field instance: Database

    // El constructor del singleton siempre debe ser privado
    // para evitar llamadas de construcción directas con el
    // operador `new`.
    private constructor Database() is
        // Algún código de inicialización, como la propia
        // conexión al servidor de una base de datos.
        // ...

    // El método estático que controla el acceso a la instancia
    // singleton.
    public static method getInstance() is
        if (Database.instance == null) then
            acquireThreadLock() and then
                // Garantiza que la instancia aún no se ha
                // inicializado por otro hilo mientras ésta ha
                // estado esperando el desbloqueo.
                if (Database.instance == null) then
                    Database.instance = new Database()
        return Database.instance

    // Por último, cualquier singleton debe definir cierta
    // lógica de negocio que pueda ejecutarse en su instancia.
        public method query(sql) is
        // Por ejemplo, todas las consultas a la base de datos
        // de una aplicación pasan por este método. Por lo
        // tanto, aquí puedes colocar lógica de regularización
        // (throttling) o de envío a la memoria caché.
        // ...

    class Application is method main() is
        Database foo = Database.getInstance()
        foo.query("SELECT ...")
        // ...
        Database bar = Database.getInstance()
        bar.query("SELECT ...")
        // La variable `bar` contendrá el mismo objeto que la
        // variable `foo`.
### Pros y Contras
| Pros | Contras|
|----------|----------|
| Puedes tener la certeza de que una clase tiene una única instancia.|Vulnera el Principio de responsabilidad única. El patrón resuelve dos problemas al mismo tiempo.|
| Obtienes un punto de acceso global a dicha instancia.| El patrón Singleton puede enmascarar un mal diseño, por ejemplo, cuando los componentes del programa saben demasiado los unos sobre los otros.|
| El objeto Singleton solo se inicializa cuando se requiere por primera vez.| El patrón requiere de un tratamiento especial en un entorno con múltiples hilos de ejecución, para que varios hilos no creen un objet°o Singleton varias veces.|
|| Puede resultar complicado realizar la prueba unitaria del código cliente del Singleton porque muchos frameworks de prueba dependen de la herencia a la hora de crear objetos simulados (mock objects). Debido a que la clase Singleton es privada y en la mayoría de los lenguajes resulta imposible sobrescribir métodos estáticos, tendrás que pensar en una manera original de simular el Singleton. O, simplemente, no escribas las pruebas. O no utilices el patrón Singleton.||
## Template
_Es un patrón de diseño de comportamiento que define el esqueleto de un algoritmo en la superclase pero permite que las subclases sobrescriban pasos del algoritmo sin cambiar su estructura._

### Pseudocodigo
_En este ejemplo, el patrón Template Method proporciona un “esqueleto” para varias ramas de inteligencia artificial (IA) en un sencillo videojuego de estrategia._
_Todas las razas del juego tienen tipos de unidades y edificios casi iguales. Por lo tanto, puedes reutilizar la misma estructura IA para varias de ellas, a la vez que puedes sobrescribir algunos de los detalles. Con esta solución, puedes sobrescribir la IA de los orcos para que sean más agresivos, hacer que los humanos tengan una actitud más defensiva y hacer que los monstruos no puedan construir nada. Para añadir una nueva raza al juego habría que crear una nueva subclase IA y sobrescribir los métodos por defecto declarados en la clase IA base._

    // La clase abstracta define un método plantilla que contiene un
    // esqueleto de algún algoritmo compuesto por llamadas,
    // normalmente a operaciones primitivas abstractas. Las
    // subclases concretas implementan estas operaciones, pero dejan
    // el propio método plantilla intacto.
      class GameAI is
    // El método plantilla define el esqueleto de un algoritmo.
    method turn() is
        collectResources()
        buildStructures()
        buildUnits()
        attack()

    // Algunos de los pasos se pueden implementar directamente
    // en una clase base.
    method collectResources() is
        foreach (s in this.builtStructures) do
            s.collect()

    // Y algunos de ellos pueden definirse como abstractos.
    abstract method buildStructures()
    abstract method buildUnits()

    // Una clase puede tener varios métodos plantilla.
    method attack() is
        enemy = closestEnemy()
        if (enemy == null)
            sendScouts(map.center)
        else
            sendWarriors(enemy.position)

    abstract method sendScouts(position)
    abstract method sendWarriors(position)

    // Las clases concretas tienen que implementar todas las
    // operaciones abstractas de la clase base, pero no deben
    // sobrescribir el propio método plantilla.
    class OrcsAI extends GameAI is
    method buildStructures() is
        if (there are some resources) then
            // Construye granjas, después cuarteles y después
            // fortaleza.

    method buildUnits() is
        if (there are plenty of resources) then
            if (there are no scouts)
                // Crea peón y añádelo al grupo de exploradores.
            else
                // Crea soldado, añádelo al grupo de guerreros.

    // ...

    method sendScouts(position) is
        if (scouts.length > 0) then
            // Envía exploradores a posición.

    method sendWarriors(position) is
        if (warriors.length > 5) then
            // Envía guerreros a posición.

    // Las subclases también pueden sobrescribir algunas operaciones
    // con una implementación por defecto.
    class MonstersAI extends GameAI is
    method collectResources() is
        // Los monstruos no recopilan recursos.

    method buildStructures() is
        // Los monstruos no construyen estructuras.

    method buildUnits() is
        // Los monstruos no construyen unidades.

### Pros y Contras
| Pros | Contras|
|----------|----------|
| Puedes permitir a los clientes que sobrescriban tan solo ciertas partes de un algoritmo grande, para que les afecten menos los cambios que tienen lugar en otras partes del algoritmo.| Algunos clientes pueden verse limitados por el esqueleto proporcionado de un algoritmo.|
| Puedes colocar el código duplicado dentro de una superclase.| Puede que violes el principio de sustitución de Liskov suprimiendo una implementación por defecto de un paso a través de una subclase.|
|| Los métodos plantilla tienden a ser más difíciles de mantener cuantos más pasos tengan.|

## Strategy
Es un patrón de diseño de comportamiento que te permite definir una familia de algoritmos, colocar cada uno de ellos en una clase separada y hacer sus objetos intercambiables.
### Pseudocodigo
_En este ejemplo, el contexto utiliza varias estrategias para ejecutar diversas operaciones aritméticas._
      
      // La interfaz estrategia declara operaciones comunes a todas
      // las versiones soportadas de algún algoritmo. El contexto
      // utiliza esta interfaz para invocar el algoritmo definido por
      // las estrategias concretas.
    interface Strategy is
    method execute(a, b)

      // Las estrategias concretas implementan el algoritmo mientras
      // siguen la interfaz estrategia base. La interfaz las hace
      // intercambiables en el contexto.
      class ConcreteStrategyAdd implements Strategy is
    method execute(a, b) is
        return a + b

    class ConcreteStrategySubtract implements Strategy is
    method execute(a, b) is
        return a - b

    class ConcreteStrategyMultiply implements Strategy is
    method execute(a, b) is
        return a * b

    // El contexto define la interfaz de interés para los clientes.
    class Context is
    // El contexto mantiene una referencia a uno de los objetos
    // de estrategia. El contexto no conoce la clase concreta de
    // una estrategia. Debe trabajar con todas las estrategias a
    // través de la interfaz estrategia.
    private strategy: Strategy

    // Normalmente, el contexto acepta una estrategia a través
    // del constructor y también proporciona un setter
    // (modificador) para poder cambiar la estrategia durante el
    // tiempo de ejecución.
    method setStrategy(Strategy strategy) is
        this.strategy = strategy

    // El contexto delega parte del trabajo al objeto de
    // estrategia en lugar de implementar varias versiones del
    // algoritmo por su cuenta.
    method executeStrategy(int a, int b) is
        return strategy.execute(a, b)


      // El código cliente elige una estrategia concreta y la pasa al
      // contexto. El cliente debe conocer las diferencias entre
      // estrategias para elegir la mejor opción.
      class ExampleApplication is
    method main() is
        Create context object.

        Read first number.
        Read last number.
        Read the desired action from user input.

        if (action == addition) then
            context.setStrategy(new ConcreteStrategyAdd())

        if (action == subtraction) then
            context.setStrategy(new ConcreteStrategySubtract())

        if (action == multiplication) then
            context.setStrategy(new ConcreteStrategyMultiply())

        result = context.executeStrategy(First number, Second number)

        Print result.
### Pros y Contras
| Pros | Contras|
|----------|----------|
| Puedes intercambiar algoritmos usados dentro de un objeto durante el tiempo de ejecución.| Si sólo tienes un par de algoritmos que raramente cambian, no hay una razón real para complicar el programa en exceso con nuevas clases e interfaces que vengan con el patrón.|
| Puedes aislar los detalles de implementación de un algoritmo del código que lo utiliza.| Los clientes deben conocer las diferencias entre estrategias para poder seleccionar la adecuada.|
| Puedes sustituir la herencia por composición.| Muchos lenguajes de programación modernos tienen un soporte de tipo funcional que te permite implementar distintas versiones de un algoritmo dentro de un grupo de funciones anónimas. Entonces puedes utilizar estas funciones exactamente como habrías utilizado los objetos de estrategia, pero sin saturar tu código con clases e interfaces adicionales.|
| Principio de abierto/cerrado. Puedes introducir nuevas estrategias sin tener que cambiar el contexto.||
