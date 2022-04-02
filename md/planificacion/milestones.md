# MVPs y Milestones

Un *minimum viable product*, o MVP, es un producto con las suficientes características capaz de atraer a los posibles clientes o usuarios tan pronto como sea posible.

Para la realización de este proyecto se ha propuesto la creación de los siguientes MPVs (o *milestones*, como se llaman en [GitHub](https://github.com/harvestcore/matroos/milestones)).

## [00 - Configuración del entorno, tests y CI](https://github.com/harvestcore/matroos/milestone/3)

**Versión objetivo:** 0.0.1

Este primer *milestone* es un paso necesario a la hora de iniciar un proyecto software. El principal propósito de este *milestone* es establecer la estructura del repositorio que se va a utilizar, los proyectos iniciales necesarios y la configuración de la integración continua.

Funcionalidad que debe incluir:

- Proyectos preparados para el desarrollo de las siguientes funcionalidades.
- Configuración de CI.

Decisiones técnicas:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Arquitectura](../analisis/arquitectura.md)

## 01 - Integración con la base de datos

**Versión objetivo:** 0.0.2

El principal objetivo de este *milestone* es la integración del componente principal del software ([`backend`](https://github.com/harvestcore/matroos/tree/develop/backend)) con base de datos (MongoDB), de forma que se puedan almacenar fácilmente los datos necesarios.

Funcionalidad que debe incluir:

- Integración de la base de datos con el [`backend`](https://github.com/harvestcore/matroos/tree/develop/backend).

Decisiones técnicas:

- [Arquitectura](../analisis/arquitectura.md)
- [Base de datos](../analisis/herramientas.md#base-de-datos)

## 02 - Creación y configuración de bots

**Versión objetivo:** 0.0.3

La finalidad de este *milestone* es la creación y configuración de bots. Para ello se ampliará la funcionalidad del proyecto de recursos compartidos ([`resources`](https://github.com/harvestcore/matroos/tree/develop/resources)) y el proyecto principal ([`backend`](https://github.com/harvestcore/matroos/tree/develop/backend)), el cual implementa el servicio que gestiona estas operaciones.

Funcionalidad que debe incluir:

- Creación y configuración de bots y comandos.
- Integración con base de datos.

Decisiones técnicas:

- [Arquitectura](../analisis/arquitectura.md)
- [Base de datos](../analisis/herramientas.md#base-de-datos)

## 03 - Creación y configuración de comandos

**Versión objetivo:** 0.0.4

El objetivo de este *milestone* es la creación y configuración de comandos, los cuales podrán ser configurados en bots para después ser utilizados en los servidores de Discord. Para ello se ampliará la funcionalidad del proyecto de recursos compartidos ([`resources`](https://github.com/harvestcore/matroos/tree/develop/resources)) y el proyecto principal ([`backend`](https://github.com/harvestcore/matroos/tree/develop/backend)), el cual implementa el servicio que gestiona estas operaciones.

Tras la finalización de este *milestone* la creación y configuración de bots mediante código será posible. Esto significa que un usuario con conocimientos más avanzados en el desarrollo de aplicaciones será capaz de crear bots y comandos de Discord, y además podrá realizar la configuración de ambos.

Funcionalidad que debe incluir:

- Creación y configuración de bots y comandos.
- Integración con base de datos.

Decisiones técnicas:

- [Arquitectura](../analisis/arquitectura.md)
- [Base de datos](../analisis/herramientas.md#base-de-datos)

## [04 - Despliegue de bots en workers](https://github.com/harvestcore/matroos/milestone/5)

**Versión objetivo:** 0.0.3

Tras la posibilidad de crear, configurar y almacenar bots, estos se deben poder desplegar. El objetivo de este *milestone* es permitir el despliegue (la ejecución) de los bots en los workers. Esto significa que un usuario con conocimientos más avanzados en el desarrollo de aplicaciones será capaz de desplegar bots que podrán ser usados en servidores de Discord.

Funcionalidad que debe incluir:

- Comunicación entre el núcleo principal y los workers.
- Despliegue de los bots en los workers.

Decisiones técnicas:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Arquitectura](../analisis/arquitectura.md)

## [05 - API REST](https://github.com/harvestcore/matroos/milestone/7)

**Versión objetivo:** 0.1.0

Una vez que tanto el componente backend como el componente escalable worker están finalizados, estos sólo son accesibles mediante código. El objetivo de este *milestone* es definir e implementar la API REST que permita realizar todas las funcionalidades implementadas en *milestones* anteriores (creación, configuración y despliegue de bots). Una vez finalizado este *milestone* el software será capaz de responder a las diferentes peticiones que se le hagan mediante la API REST.

Funcionalidad que debe incluir:

- Endpoints de la API REST.

Decisiones técnicas:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Arquitectura](../analisis/arquitectura.md)

## [06 - Despliegue en contenedores Docker](https://github.com/harvestcore/matroos/milestone/3)

**Versión objetivo:** 0.2.0

Tras desarrollar la *API REST*, el software está listo para ser distribuido. Este *milestone* se centra en la distribución del software mediante contenedores Docker.

Funcionalidad que debe incluir:

- Archivo *Dockerfile* para el microservicio del *backend*.
- Archivo *Dockerfile* para el microservicio del *worker*.
- Archivo *Docker Compose* para orquestar los microservicios.

Decisiones técnicas:

- [Despliegue en contenedores](../analisis/herramientas.md#despliegue-en-contenedores)

## [07 - Interfaz de usuario](https://github.com/harvestcore/matroos/milestone/9)

**Versión objetivo:** 0.3.0

El objetivo de este *milestone* es la creación de una interfaz de usuario capaz de realizar las tareas de creación y configuración de comandos y bots, además del despliegue de estos.

La interfaz de usuario no es un componente imprescindible para el funcionamiento del sistema en su conjunto, por lo que en caso de que no se contase con el tiempo necesario para su desarrollo, este podría posponerse (pasando entonces al *milestone* siguiente).

Funcionalidad que debe incluir:

- Interfaz concluida.
- Archivo Dockerfile para el microservicio.

Decisiones técnicas:

- [Frontend](../analisis/herramientas.md#frontend)
- [Arquitectura](../analisis/arquitectura.md)

## [08 - Despliegue cloud](https://github.com/harvestcore/matroos/milestone/4)

**Versión objetivo:** 0.4.0

El objetivo es el despliegue y configuración de los microservicios en una plataforma Cloud.

Funcionalidad que debe incluir:

- Microservicios desplegados y configurados en la plataforma Cloud elegida.

Decisiones técnicas:

- [Arquitectura](../analisis/arquitectura.md)
