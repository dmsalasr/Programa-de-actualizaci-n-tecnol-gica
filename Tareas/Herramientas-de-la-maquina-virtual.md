# Herramientas
## zsh-shell
_Es un potente terminal de comandos para sistemas operativos basados en Unix como GNU/Linux o macOS. Este terminal se diseño para poder utilizarse de manera interactiva con el usuario. Además se incluyen las principales características de otros terminales de Unix como bash, ksh o tcsh._
#### Para instalarlo se requiere del siguiente comando:
    sudo apt install zsh
    
## Git
_Es un sistema de control de versiones distribuido, lo que significa que un clon local del proyecto es un repositorio de control de versiones completo. Estos repositorios locales plenamente funcionales permiten trabajar sin conexión o de forma remota con facilidad._
#### El flujo de trabajo básico en Git es algo así:
1. Modificas una serie de archivos en tu directorio de trabajo.
1. Preparas los archivos, añadiéndolos a tu área de preparación.
1. Confirmas los cambios, lo que toma los archivos tal y como están en el área de preparación y almacena esa copia instantánea de manera permanente en tu directorio de Git.
## oh-myzsh
_Es un paquete de utilidades, plugins y plantillas para el shell ZSH.Nos permite entre otras funciones el autocompletado de nombres de comando de archivos, funciones avanzadas de para realizar scripting, consulta del historial de comandos usados, colores configurables entre otras funciones._
#### Funcionalidades:
- Autocompletado mejorada de la línea de comandos (no diferencia entre mayúsculas minúsculas).
- Autocompletado de comandos Git. Visualización de información relativa a Git cuando nos situamos en un directorio que contiene un repositorio de código. Nos informa de la rama actual en la que nos encontramos así como el estado actual informando si tenemos cambios que subir en local.
- Instalación de plugins adicionales para permitir complementar la funcionalidad base (ej: autocompletado de comandos docker, autocompletado Gitflow).
- Permite la creación de alias globales.
- Diferentes temas disponibles para personalizar tu experiencia durante tiempo de uso de tu terminal.
#### Para instalarlo se requiere del siguiente comando:
_Hay que tener en cuenta que previamente a poder instalar Oh My ZSH, necesitamos tener configurada y funcionando la shell ZSH, por lo que procedemos a su instalación desde cero:_

    sudo apt-get install git zsh

_Despues de esto ya se podra instalar para usarlo con el siguiente comando:_
   
    sudo apt install -y zsh
### agnoster
_Ahora que Zsh y OhMyZsh están instalados, puedes continuar configurando el tema de tu terminal. Para ello, primero debe descargar una fuente que admita los caracteres e íconos únicos utilizados por el tema._

    sudo apt instalar fuentes-powerline

  _Después de instalar la fuente, puede habilitar el tema Agnoster cambiando la variable ZSH_THEME dentro del archivo de configuración ~/.zshrc ._

    ZSH_THEME = "agnoster"

 ## docker
 _Docker es una plataforma de software que le permite crear, probar e implementar aplicaciones rápidamente. Docker empaqueta software en unidades estandarizadas llamadas contenedores que incluyen todo lo necesario para que el software se ejecute, incluidas bibliotecas, herramientas de sistema, código y tiempo de ejecución. Con Docker, puede implementar y ajustar la escala de aplicaciones rápidamente en cualquier entorno con la certeza de saber que su código se ejecutará._

 ### Cómo funciona Docker
 _Docker le proporciona una manera estándar de ejecutar su código. Docker es un sistema operativo para contenedores. De manera similar a cómo una máquina virtual virtualiza (elimina la necesidad de administrar directamente) el hardware del servidor, los contenedores virtualizan el sistema operativo de un servidor. Docker se instala en cada servidor y proporciona comandos sencillos que puede utilizar para crear, iniciar o detener contenedores._
 ### Ventajas de usar contenedores Docker
- Portabilidad
- Eficiencia
- Flexibilidad
- Escalabilidad
- Aislamiento
- Reproducibilidad

## docker-compose
_Es una herramienta para definir y ejecutar aplicaciones de Docker de varios contenedores. En Compose, se usa un archivo YAML para configurar los servicios de la aplicación. Después, con un solo comando, se crean y se inician todos los servicios de la configuración._
### Requisitos previos 
- Suscripción a Azure. Si no tiene una, cree una cuenta gratuita antes de empezar.
- Motor de Docker. Confirme que la CLI de Docker funciona en una ventana de consola.
- Un recurso de Azure con el plan de tarifa correcto. Solo los siguientes planes de tarifa funcionan con este contenedor:


1. El recurso de Visión de Azure AI solo con el plan de tarifa estándar o F0.
1. El recurso Documento de inteligencia solo con el plan de tarifa estándar o F0. 
1. El recurso servicios de Azure AI con el plan de tarifas S0. >
- Si va a usar un contenedor de versión preliminar validada, deberá completar para ello el formulario de solicitud en línea.

## sdkMan
_Es una herramienta para manejar múltiples versiones de distintos SDKs en sistemas Unix (aunque también existe una versión alternativa para Windows). Proporciona una interfaz de línea de comandos y un API para instalar, cambiar, eliminar y mostrar la lista de candidatos._
#### Para instalarlo se requiere del siguiente comando:

    $ curl -s "https://get.sdkman.io" | bash
## Java 8, 11 y 17

| | Entorno de ejecución de Java 8 | Entornos de ejecución de Java 11/17 |
|----------|----------|----------|
| Implementación del servidor	 |Servidor implementado a través de Jetty   | Si la app no usa los servicios agrupados en paquetes heredados, debes implementar un servidor tú mismo. |
| Servicios en paquetes heredados de App Engine	 | Proporcionado   |  Proporcionado  |
| Capacidad de usar las bibliotecas cliente de Cloud para Java    | Si   | Si |
| Extensión del lenguaje y compatibilidad con la biblioteca del sistema | Si | Si |
| Acceso a la red externa| Si | Si |
| Acceso al sistema de archivos |Acceso de lectura/escritura a /tmp	| Acceso de lectura/escritura a /tmp |
| Entorno de ejecución del lenguaje	| Modificado para App Engine |  Entorno de ejecución de código abierto no modificado |
| Logging	|  Usa un java.util.logging.ConsoleHandler, que escribe en stderr y limpia la transmisión después de cada registro.| Cloud Logging estándar|
## Maven
_Es una herramienta de software para la gestión y construcción de proyectos Java creada por Jason van Zyl, de Sonatype, en 2002. Es similar en funcionalidad a Apache Ant, pero tiene un modelo de configuración de construcción más simple, basado en un formato XML_
#### Para instalarlo se requiere del siguiente comando:
    $ wget https://mirrors.estointernet.in/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
    $ tar -xvf apache-maven-3.6.3-bin.tar.gz
    $ mv apache-maven-3.6.3 /opt/
## Eclipse
_Es un entorno de desarrollo software multi-lenguaje construido alrededor de un workspace al que pueden incluirse un gran número de plugins que proporcionan funcionalidades concretas relacionadas con lenguajes específicos o con la interacción con otras herramientas implicadas en el desarrollo de una aplicación._
## VisualStudioCode
_Es un editor de código fuente desarrollado por Microsoft para Windows, Linux, macOS y Web. Incluye soporte para la depuración, control integrado de Git, resaltado de sintaxis, finalización inteligente de código, fragmentos y refactorización de código._
## sudo
_El programa sudo es una utilidad de los sistemas operativos tipo Unix, como GNU/Linux, BSD, Mac OS X o Mac OS 11, que permite a los usuarios ejecutar programas con los privilegios de seguridad de otro usuario de manera segura, convirtiéndose así temporalmente en el otro usuario durante la ejecución del programa_
## apt update
_Es usado para actualizar los paquetes_
## apt install (apt-get)
_Funciona para instalar programas o paquetes._
## Utilerías Linux
### curl
_Es un proyecto de software consistente en una biblioteca y un intérprete de comandos orientado a la transferencia de archivos. Soporta los protocolos FTP, FTPS, HTTP, HTTPS, TFTP, SCP, SFTP, Telnet, DICT, FILE y LDAP, entre otros._
### telnet
_Es el nombre de un protocolo de red que nos permite acceder a otra máquina para manejarla remotamente como si estuviéramos sentados delante de ella. También es el nombre del programa informático que implementa el cliente_
### wget
_Es una herramienta informática creada por el Proyecto GNU. Puedes usarlo para recuperar contenido y archivos de varios servidores web. El nombre es una combinación de World Wide Web y la palabra get. Admite descargas a través de FTP, SFTP, HTTP y HTTPS._
### tree
_Es un comando bastante utilizado por los usuarios de Linux, que nos permite mostrar de manera gráfica y de forma estructurada la jerarquía de los directorios de nuestro sistema operativo.El comando tree además permite listar los directorios de los dispositivos externos._
## NVM
_Es un administrador de versiones para node.js , diseñado para instalarse por usuario e invocarse por shell. nvmfunciona en cualquier shell compatible con POSIX (sh, dash, ksh, zsh, bash), en particular en estas plataformas: Unix, macOS y Windows WSL ._
#### Para instalarlo se requiere del siguiente comando:
    $curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
## NodeJS
_Es un entorno en tiempo de ejecución multiplataforma, de código abierto, para la capa del servidor basado en el lenguaje de programación JavaScript, asíncrono, con E/S de datos en una arquitectura orientada a eventos y basado en el motor V8 de Google._

#### Para instalarlo se requiere del siguiente comando:
    $curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
    $sudo apt-get install -y nodejs
## npm
_Es el Node Package Manager que viene incluido y ayuda a cada desarrollo asociado a Node. Durante años, Node ha sido ampliamente utilizado por los desarrolladores de JavaScript para compartir herramientas, instalar varios módulos y administrar sus dependencias. Es por eso que es fundamental que las personas que trabajan con Node.js entiendan qué es npm._
#### Para instalarlo se requiere del siguiente comando:

    $sudo apt-get install nodejs npm
## md5, sha
_Son algoritmos de resumen de mensaje derivados de MD4. Las funciones hash SHA (Secure Hash Algorithm) son el resultado del trabajo de la National Security Agency (NSA) para suministrar potentes funciones de hash criptográficas. Los errores de seguridad se identifican en SHA-1 y MD5._
## Postman
_Es una plataforma que permite y hace más sencilla la creación y el uso de APIs. Esta herramienta es muy útil para programar porque da la posibilidad hacer pruebas y comprobar el correcto funcionamiento de los proyectos que realizan los desarrolladores web. ¡Todo en base a una extensión en Google Chrome!_
## MySQL Workbench
_Es una herramienta visual de diseño de bases de datos que integra desarrollo de software, administración de bases de datos, diseño de bases de datos, gestión y mantenimiento para el sistema de base de datos MySQL_
## VueJs
_Es un framework de JavaScript de código abierto para la construcción de interfaces de usuario y aplicaciones de una sola página. Fue creado por Evan You, y es mantenido por él y por el resto de los miembros activos del equipo central que provienen de diversas empresas como Netlify y Netguru._
