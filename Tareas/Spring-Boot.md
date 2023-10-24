# Spring Boot
## ¿Qué es Spring Boot?
_Spring Boot es un framework desarrollado para el trabajo con Java como lenguaje de programación. Se trata de un entorno de desarrollo de código abierto y gratuito. Spring Boot cuenta con una serie de características que han incrementado su popularidad y, en consecuencia, su uso por parte de los desarrolladores back-end. Estas son las características más destacadas de este framework:_
- Permite crear todo tipo de aplicaciones en el lado del back-end de forma independiente.
- Facilita el trabajo con otras herramientas como Tomcat, Jetty o Undertow. Lo hace directamente, sin necesidad de implementar archivos específicos para ello.
- Simplifica las dependencias para mejorar la configuración final del proyecto que se desarrolla con Spring Boot.
- Se trata de un framework que se configura de manera simple y es compatible con bibliotecas de terceros.
- Facilita la creación de listas, controles de estado y mejora la configuración externa para el desarrollo de aplicaciones.
- No es necesario generar código para los aspectos que controla Spring Boot y no hay requisitos para la configuración XML.


## ¿Qué es un controlador?
_El controlador es responsable de manejar las solicitudes HTTP entrantes y enviar respuestas. Por lo general, recibe datos del usuario a través de la solicitud, delega en un servicio para realizar la lógica de negocio y luego envía una respuesta al usuario._

## Definición y características de un servicio REST
### Definición
_Es una arquitectura de software que impone condiciones sobre cómo debe funcionar una API. En un principio, REST se creó como una guía para administrar la comunicación en una red compleja como Internet._
### características de un servicio REST
_REST no es un estándar, simplemente define unos principios de arquitectura a seguir para implementar aplicaciones o servicios en red. Sin embargo, REST se basa en estándares para su implementación: HTTP, XML, etc. Los servicios REST tienen las siguientes características:_
- Cliente-Servidor
  
_Los servicios REST deben estar basados en una arquitectura Cliente-Servidor. Un servidor que contiene los recursos y estados de los mismos, y unos clientes que acceden a ellos._

- Sin estado
  
_Los Servicios REST pueden ser escalados hasta alcanzar grandes rendimientos para abarcar la demanda de todos los posibles clientes. Esto implica que sea necesario crear granjas de servidores con balanceo de cargas y failover o diferentes niveles de servidores para minimizar el tiempo de respuesta a los clientes. Al utilizar servidores intermedios, es necesario que los clientes REST envíen la información completa e independiente en cada solicitud de estado de un recurso._

- Información cacheable
  
_Para mejorar la eficiencia en el tráfico de red, las respuestas del servidor deben tener la posibilidad de ser marcadas como cacheables. Esta información es utilizada por los clientes REST para decidir si hacer una copia local del recurso con la fecha y hora del último cambio de estado del recurso._

* Interfaz uniforme
Una de las características principales de los servicios Web REST es el uso explícito de métodos HTTP (HyperText Transfer Protocol). Estos métodos son indicados en la cabecera HTTP por parte del cliente y son los siguientes:
  * GET: recoge información de un recurso
  * PUT: modifica o actualiza el estado de un recurso
  * POST: crea un nuevo recurso en el servidor
  * DELETE: elimina un recurso del servidor.

- Respuesta en un formato conocido
  
_La representación de un recurso refleja el estado actual del mismo y sus atributos en el instante en el que el cliente ha realizado la solicitud. Este resultado puede representar simplemente el valor de una variable en un instante de tiempo, un registro de una Base de Datos o cualquier otro tipo de información._
