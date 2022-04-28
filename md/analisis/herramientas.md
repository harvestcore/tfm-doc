# Herramientas

## Control de versiones

Para el control de versiones se utiliza Git, ya que es la herramienta de este tipo que mejor manejo. Por otro lado, para alojar los repositorios se utiliza GitHub, que al igual que antes, es la que mejor manejo y en la que tengo todos mis proyectos personales alojados. Existen alternativas, como [GitLab](https://about.gitlab.com/) o [Bitbucket](https://bitbucket.org/product/), pero o bien son a mi parecer algo mas complejas o requieren suscripciones para acceder a algunas de las características más interesantes.

## Integración continua (CI)

La integración continua la práctica que incluye el control de la versión del código desarrollado y la prueba automática del mismo de forma regular para detectar rápidamente errores. Actualmente es un requisito necesario e indispensable para cualquier tipo de software, y todos los aspectos del mismo deben ser atendidos.

En este proyecto se utiliza *GitHub Actions* como sistema de integración continua. Esto se debe a dos razones, en primer lugar, el proyecto está alojado en *GitHub* y, por otro lado, *GitHub Actions* tiene una flexibilidad increíble, por lo que se puede establecer de manera sencilla cualquier tipo de entorno para las pruebas. Por otro lado permite desplegar contenedores Docker, lo cual es útil para cuando se quieran ejecutar tests de integración con la base de datos.

Existen otros servicios para este tipo de pruebas, como son Jenkins, Travis CI o Circle CI. Todos ellos, junto con GitHub Actions, comparten características y son realmente similares. Sin embargo, algunos de estos no son completamente gratuitos, y otros requieren de un esfuerzo extra para desplegarlos y ponerlos en funcionamiento, algo que creo que no merece la pena teniendo una herramienta disponible en el mismo repositorio en el que se aloja el código.

## Base de datos

La elección de un sistema de gestión de bases de datos es una de las decisiones más importantes a la hora de diseñar y desarrollar software. Hay muchos tipos de bases de datos, y hay una serie de cuestiones que deben tenerse en cuenta al elegir una.

Actualmente existen dos principales tipos de bases de datos: SQL y NoSQL.

Las bases de datos SQL se basan en las relaciones entre los datos, los cuales se introducen en registros y luego se ordenan por tablas, columnas y tuplas. El lenguaje de consulta principal es SQL. Su principal característica es el esquema rígido predefinido, que garantiza un esquema *ACID*. En el caso de las bases de datos NoSQL, no tienen esquema rígido, siendo mucho más versátiles que las primeras. Las hay de distintos subtipos, ya que se pueden basar en estructuras clave-valor, en documentos, grafos u orientadas a objetos.

Por la naturaleza del proyecto, se descarta el modelo relacional y el tipo SQL, ya que los tipos de datos a procesar no necesitan tener una gran relación entre ellos. Sólo se necesita relacionar comandos con bots, y adicionalmente se necesita almacenar una serie de parámetros para los comandos (sin un esquema rígido definido). Por lo tanto se va a usar una base de datos NoSQL basada en documentos, MongoDB.

Por otro lado, el tipo de consulta a ejecutar en este proyecto no son complejas. Teniendo en cuenta esto, cabe destacar otra ventaja de las bases de datos NoSQL, la velocidad de ejecución de las consultas.

Para la integración de la base de datos en el software se utilizan los ORM (Object Relational Mapper), los cuales permiten realizar consultas de manera sencilla utilizando las características del lenguaje que se desee. MongoDB dispone de una gran variedad de conectores para multitud de lenguajes de programación, y la API que provee es realmente sencilla. Además, los datos se almacenan en formato BSON (Binary JSON), que da más flexibilidad que el formato JSON tradicional.

DBaaS (Database as a Service) es un concepto que en los últimos años está destacando bastante. Este servicio brinda un entorno que ofrece bases de datos optimizadas para operaciones en entornos virtualizados y además garantiza conceptos como la escalabilidad o la alta disponibilidad.

## Lenguaje de programación

### Backend y Workers

En la actualidad existe una gran variedad de lenguajes de programación que podrían usarse para desarrollar el software con las características que se requieren. En concreto, algunos de estos lenguajes son JavaScript, Java, C#, Python, Ruby, PHP, Go y Kotlin.

Teniendo en cuenta las características requeridas, se observa que:

- Para el manejo de datos se requiere que se pueda conectar a MongoDB y esto lo cumplen todos los lenguajes anteriores.
- En cuanto a Discord, se requiere algún SDK que tenga soporte con el lenguaje, y la mayoría de los lenguajes mencionados lo tienen.

Se elige C# como lenguaje para el desarrollo de la parte backend por distintos motivos:

- Es independiente de la plataforma en la que se ejecute.
- Flexible.
- Orientado a objetos.
- Rico en librerías.
- Lenguaje compilado.
- Buen rendimiento.
- IDE muy bien integrado (Visual Studio).
- Buena comunidad, siendo uno de los lenguajes más usados.
- Actualizado con regularidad.
- Fuertemente tipado.
- Asincronía y tareas en segundo plano.

Aún teniendo grandes ventajas sobre otros lenguajes, también tiene inconvenientes:

- Compilado en dos fases, algo que ralentiza este proceso.
- Curva de aprendizaje superior a otros lenguajes.

También se han tenido en cuenta otros lenguajes de programación, también muy populares para el desarrollo de software de este tipo. Estos son:

- Java. Con sintaxis y rendimiento similar a C#.
- JavaScript / TypeScript. Con peor rendimiento que C#.
- Python. Peor rendimiento que C#. Además es un lenguaje interpretado y no tiene un tipado tan fuerte.
- Ruby. Similar a Python.
- Go. Similar en rendimiento, pero con características muy distintas y una comunidad más pequeña al ser un lenguaje reciente.

#### Framework

Una vez seleccionado C# como lenguaje de programación, se elige **.NET Core** como framework. Es el más popular, más utilizado y con más soporte. Existe otra versión más extensa que incluye soporte para vistas (siguiendo el patrón MVC), pero esa no tiene especial relevancia en el software que se desarrolla. También cabe destacar que en su última versión, la 6, el rendimiento ha mejorado mucho respecto a versiones anteriores, lo que ha hecho que se sitúe en mejor posición respecto a otros frameworks de desarrollo web backend.

Se han tenido en cuenta otros frameworks de otros lenguajes de programación:

- Spring, de Java.
- FastAPI y Flask, de Python.
- Express, de JavaScript y TypeScript.
- Ruby on Rails, de Ruby.
- Revel y Beego, de Go.

Estos, aun siendo similares, presentan menor rendimiento, o tienen características que dificultan el desarrollo.

#### Logs

Los logs son realmente importantes, ya que facilitan la trazabilidad de errores y problemas en un sistema. Para el desarrollo del backend se utiliza Serilog, la cual es una librería muy sencilla y muy potente, además de la más utilizada, para *loggear* una aplicación. Además, esta librería incluye diversos "conectores", que permiten almacenar los logs en archivos de texto plano o en bases de datos. En concreto se va a utilizar:

- Serilog
- Serilog.Sinks.MongoDB
- Serilog.Sinks.File

### Frontend

Se utiliza TypeScript. Es igual que JavaScript pero con las ventajas del tipado. La principal desventaja es que tiene que ser compilado a JavaScript.

#### Framework

Para desarrollar la interfaz web se utiliza Next.js. Este framework se basa en React y otras librerías y permite crear y desplegar interfaces web de manera sencilla, preparadas para un entorno de producción. Aparte de las mencionadas, de sus características destacan las siguientes:

- Optimización de rendimiento frente a React.
- Compilado a JS más rápido.
- Rutas dinámicas.
- Posibilidad de usar SSR (Server-Side Rendering).
- Compatibilidad con multitud de librerías de CSS.
- Simplifica las dependencias necesarias para el desarrollo del software.

De forma paralela a Next.js, existen otros frameworks también muy conocidos. Estos son: React, el cual se puede utilizar de manera individual. Vue, un framework muy interesante con características similares a React, ya que ambos trabajan con un DOM virtual y manejan los estados de un modo parecido. Y Angular, que es el que presenta mayores diferencias, ya que la organización interna de los componentes difiere completamente de los demás y además maneja el estado de manera distinta a los demás.

## Despliegue en contenedores

Para el despliegue del software en contenedores se utiliza Docker, tanto para el frontend, como para el backend y los workers.

Docker es un sistema proporciona una capa adicional de abstracción y virtualización de aplicaciones, lo que nos permite ejecutar software de forma independiente sin depender de configuraciones complejas de máquinas virtuales o hipervisores. Por otro lado, los recursos también se pueden aislar.

Para crear estos contenedores se utilizan los llamados Dockerfiles, que son archivos de texto plano con distintas instrucciones para crear a voluntad el entorno de ejecución de nuestro software. En el caso de este proyecto, será necesario crear al menos tres de estos archivos (frontend, backend y worker). La creación de la imagen se realizará en un *pipeline* de GitHub Actions y ésta se alojará en el registro de imágenes de GitHub (ghcr.io).

Docker Compose es otra herramienta adicional que facilita el proceso de construcción y despliegue de contenedores, ya que permite realizar las configuraciones necesarias en un sencillo archivo YAML. Uno de estos archivos también se incluye en el proyecto.

Por último, existen otras herramientas muy interesantes como Kubernetes, OpenShift o Mesos que nos permiten orquestar y escalar contenedores según criterios configurados. No se usan en este proyecto, pero si se quiere ir un paso más allá en la implementación del software, pueden ser muy interesantes.
