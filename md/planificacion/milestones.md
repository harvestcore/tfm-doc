# MVPs y Milestones

Un *minimum viable product*, o MVP, es un producto con las suficientes características capaz de atraer a los posibles clientes o usuarios tan pronto como sea posible.

Para la realización de este proyecto se ha propuesto la creación de los siguientes MPVs (o *milestones*, como se llaman en [GitHub](https://github.com/harvestcore/matroos/milestones)).

Los milestones 0 a 6 son los principales del proyecto, y son los que se planea inicialmente realizar. Los milestones 7 y 8 son adicionales, y completarían el desarrollo de todo el software incluyendo funcionalidad y características extra.

## Milestones principales

### [00 - Configuración del entorno, tests y CI](https://github.com/harvestcore/matroos/milestone/3)

**Versión objetivo:** 0.0.1

Tras la finalización de este *milestone*:

- La estructura del repositorio está definida e implementada.
- Los proyectos necesarios (`recursos`, `backend` y `worker`) están creados y listos para continuar con el desarrollo de nuevas funcionalidades.
- CI está listo para ejecutar los diferentes tests y pruebas implementadas en los distintos proyectos.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Integración continua](../analisis/herramientas.md#integración-continua-ci)
- [Arquitectura](../analisis/arquitectura.md)

### 01 - Modelado de datos y lógica de negocio

**Versión objetivo:** 0.0.2

Tras la finalización de este *milestone*:

- Los datos necesarios están modelados.
- La lógica de negocio en su forma más básica está definida.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Arquitectura](../analisis/arquitectura.md)
- [Comandos](../diseño/comandos.md)
- [Bots](../diseño/bots.md)
- [Herramientas](../analisis/herramientas.md)

### [02 - Gestión de comandos](https://github.com/harvestcore/matroos/milestone/10)

**Versión objetivo:** 0.0.3

Tras la finalización de este *milestone*:

- La estructura de los comandos está definida.
- El [`backend`](https://github.com/harvestcore/matroos/tree/develop/backend) cuenta con un servicio capaz de gestionar los comandos y su configuración.
- Los cuatro tipos de comandos básicos quedan definidos y se pueden crear nuevos comandos de estos tipos.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Arquitectura](../analisis/arquitectura.md)
- [Comandos](../diseño/comandos.md)

### [03 - Gestión de bots](https://github.com/harvestcore/matroos/milestone/6)

**Versión objetivo:** 0.0.4

Tras la finalización de este *milestone*:

- La estructura de los bots está definida.
- El [`backend`](https://github.com/harvestcore/matroos/tree/develop/backend) cuenta con un servicio capaz de gestionar los bots y su configuración.
- Es posible asociar comandos a bots.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Arquitectura](../analisis/arquitectura.md)
- [Bots](../diseño/bots.md)

### [04 - Despliegue de bots en workers](https://github.com/harvestcore/matroos/milestone/5)

**Versión objetivo:** 0.0.5

Tras la finalización de este *milestone*:

- Es posible desplegar (ejecutar) bots en los workers.
- El backend es capaz de comunicarse con los distintos workers.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Arquitectura](../analisis/arquitectura.md)

### [05 - API REST](https://github.com/harvestcore/matroos/milestone/7)

**Versión objetivo:** 0.1.0

Tras la finalización de este *milestone*:

- La `API Rest` está definida y los *endpoints* están documentados.
- Es posible realizar las tareas de administración de bots y comandos haciendo uso de la API.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Lenguaje de programación y framework](../analisis/herramientas.md#lenguaje-de-programación)
- [Arquitectura](../analisis/arquitectura.md)

### [06 - Despliegue en contenedores Docker](https://github.com/harvestcore/matroos/milestone/2)

**Versión objetivo:** 0.2.0

Tras la finalización de este *milestone*:

- El software es distribuible mediante contenedores Docker.
- El archivo *Dockerfile* para el microservicio del *backend* está disponible.
- El archivo *Dockerfile* para el microservicio del *worker* está disponible.
- El archivo *Docker Compose* para orquestar los microservicios está disponible.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Despliegue en contenedores](../analisis/herramientas.md#despliegue-en-contenedores)
- [Arquitectura](../analisis/arquitectura.md)

### [07 - Almacén de datos](https://github.com/harvestcore/matroos/milestone/11)

**Versión objetivo:** 0.3.0

Tras la finalización de este *milestone*:

- Tanto los bots como los comandos son almacenables en base de datos (MongoDB).
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Herramientas (BD)](../analisis/herramientas.md#base-de-datos)
- [Arquitectura](../analisis/arquitectura.md)
- [Base de datos](../diseño/base-datos.md)

---

## Milestones adicionales

### [08 - Interfaz de usuario](https://github.com/harvestcore/matroos/milestone/9)

**Versión objetivo:** 0.4.0

Tras la finalización de este *milestone*:

- La interfaz de usuario está disponible y es capaz de realizar las tareas de creación y configuración de comandos y bots, además del despliegue de éstos en workers.
- La interfaz de usuario es distribuible mediante contenedores Docker.
- El archivo Dockerfile para el microservicio está disponible.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Frontend](../analisis/herramientas.md#frontend)
- [Arquitectura](../analisis/arquitectura.md)

### [09 - Despliegue cloud](https://github.com/harvestcore/matroos/milestone/4)

**Versión objetivo:** 0.5.0

Tras la finalización de este *milestone*:

- El software compuesto por los distintos microservicios es desplegable en un servicio cloud.
- Los archivos de configuración necesarios están disponibles.
- La documentación relacionada con el milestone está actualizada y disponible.

Decisiones técnicas y documentación adicional:

- [Arquitectura](../analisis/arquitectura.md)
- Servicio cloud aún por determinar.
