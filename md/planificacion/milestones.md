# MVPs y Milestones

Un *minimum viable product*, o MVP, es un producto con las suficientes características capaz de atraer a los posibles clientes o usuarios tan pronto como sea posible.

Para la realización de este proyecto se ha propuesto la creación de los siguientes MPVs (o *milestones*, como se llaman en [GitHub](https://github.com/harvestcore/matroos/milestones)).

## [00 - Configuración del entorno, tests y CI](https://github.com/harvestcore/matroos/milestone/3)

**Versión objetivo:** 0.0.1

Este *milestone* establece la estructura del repositorio que se va a utilizar, los proyectos iniciales necesarios y la configuración de la integración continua.

Funcionalidad que debe incluir:

- Proyectos preparados para el desarrollo de las siguientes funcionalidades.
- Configuración de CI.

Decisiones técnicas:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Arquitectura](../analisis/arquitectura.md)

## [01 - Almacén de datos](https://github.com/harvestcore/matroos/milestone/11)

**Versión objetivo:** 0.0.2

Este *milestone* incluye la integración del componente principal del software ([`backend`](https://github.com/harvestcore/matroos/tree/develop/backend)) con base de datos (MongoDB) mediante la implementación de un servicio, de forma que es posible almacenar fácilmente todos los datos necesarios.

Funcionalidad que incluye:

- Integración de la base de datos con el [`backend`](https://github.com/harvestcore/matroos/tree/develop/backend).

Decisiones técnicas:

- [Herramientas (BD)](../analisis/herramientas.md#base-de-datos)
- [Arquitectura](../analisis/arquitectura.md)
- [Base de datos](../diseño/base-datos.md)

## [02 - Gestión de bots](https://github.com/harvestcore/matroos/milestone/6)

**Versión objetivo:** 0.0.3

Este *milestone* incluye la posibilidad de creación configuración de bots. Amplía la funcionalidad del proyecto de recursos compartidos ([`resources`](https://github.com/harvestcore/matroos/tree/develop/resources)) y el proyecto principal ([`backend`](https://github.com/harvestcore/matroos/tree/develop/backend)), el cual implementa el módulo que gestiona estas operaciones.

Funcionalidad que incluye:

- Creación y configuración de bots.

Decisiones técnicas:

- [Arquitectura](../analisis/arquitectura.md)
- [Base de datos](../diseño/base-datos.md)

## [03 - Gestión de comandos](https://github.com/harvestcore/matroos/milestone/10)

**Versión objetivo:** 0.0.4

Este *milestone* incluye la posibilidad de creación y configuración de comandos, los cuales podrán ser configurados en bots para después ser utilizados en los servidores de Discord. Amplía la funcionalidad del proyecto de recursos compartidos ([`resources`](https://github.com/harvestcore/matroos/tree/develop/resources)) y el proyecto principal ([`backend`](https://github.com/harvestcore/matroos/tree/develop/backend)), el cual implementa el servicio que gestiona estas operaciones.

Tras la finalización de este *milestone* la creación y configuración de bots mediante código será posible. Esto significa que un usuario con conocimientos más avanzados en el desarrollo de aplicaciones será capaz de crear bots y comandos de Discord, y además podrá realizar la configuración de ambos.

Funcionalidad que incluye:

- Creación y configuración de comandos.

Decisiones técnicas:

- [Arquitectura](../analisis/arquitectura.md)
- [Base de datos](../diseño/base-datos.md)
- [Comandos](../diseño/comandos.md)

## [04 - Despliegue de bots en workers](https://github.com/harvestcore/matroos/milestone/5)

**Versión objetivo:** 0.0.5

Este *milestone* habilita el despliegue (la ejecución) de los bots en los workers. Tras la finalización de este milestone, un usuario con conocimientos más avanzados en el desarrollo de aplicaciones será capaz de desplegar bots que podrán ser usados en servidores de Discord.

Funcionalidad que incluye:

- Comunicación entre el núcleo principal y los workers.
- Despliegue de los bots en los workers.

Decisiones técnicas:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Arquitectura](../analisis/arquitectura.md)

## [05 - API REST](https://github.com/harvestcore/matroos/milestone/7)

**Versión objetivo:** 0.1.0

Este *milestone* define e implementa la API REST que permita realizar todas las funcionalidades implementadas en *milestones* anteriores (creación, configuración y despliegue de bots). Una vez finalizado este *milestone* el software será capaz de responder a las diferentes peticiones que se le hagan mediante la API REST.

Funcionalidad que incluye:

- Endpoints de la API REST.

Decisiones técnicas:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Arquitectura](../analisis/arquitectura.md)

## [06 - Despliegue en contenedores Docker](https://github.com/harvestcore/matroos/milestone/2)

**Versión objetivo:** 0.2.0

Este *milestone* incluye la distribución del software mediante contenedores Docker.

Funcionalidad que incluye:

- Archivo *Dockerfile* para el microservicio del *backend*.
- Archivo *Dockerfile* para el microservicio del *worker*.
- Archivo *Docker Compose* para orquestar los microservicios.

Decisiones técnicas:

- [Despliegue en contenedores](../analisis/herramientas.md#despliegue-en-contenedores)
- [Arquitectura](../analisis/arquitectura.md)

## [07 - Interfaz de usuario](https://github.com/harvestcore/matroos/milestone/9)

**Versión objetivo:** 0.3.0

Este *milestone* integra una interfaz de usuario, la cual es capaz de realizar las tareas de creación y configuración de comandos y bots, además del despliegue de estos en los diferentes workers.

La interfaz de usuario no es un componente imprescindible para el funcionamiento del sistema en su conjunto, por lo que en caso de que no se contase con el tiempo necesario para su desarrollo, este podría posponerse (pasando entonces al *milestone* siguiente).

Funcionalidad que incluye:

- Interfaz de usuario.
- Archivo Dockerfile para el microservicio.

Decisiones técnicas:

- [Frontend](../analisis/herramientas.md#frontend)
- [Arquitectura](../analisis/arquitectura.md)

## [08 - Despliegue cloud](https://github.com/harvestcore/matroos/milestone/4)

**Versión objetivo:** 0.4.0

El milestone incluye la configuración necesaria para el despliegue de la arquitectura de microservicios de Matroos en una plataforma Cloud.

Funcionalidad que incluye:

- Microservicios desplegados y configurados en la plataforma Cloud elegida.

Decisiones técnicas:

- [Arquitectura](../analisis/arquitectura.md)
