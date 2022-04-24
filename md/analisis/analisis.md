# Análisis

## Descripción de actores

- **Administrador**: Crea los bots y los comandos. Tiene poder de configuración y de despliegue. Puede ser también usuario del bot. Agrega los bots a los servidores de Discord.
- **Usuario de Discord**: No realiza ningún tipo de configuración de los bots o comandos. Interactúa con los bots una vez ya han sido configurados y desplegados por un usuario administrador. Hace uso de los comandos configurados en el bot.

## Requisitos del sistema

### Requisitos funcionales

1. El sistema tendrá un sistema de autenticación.
2. El backend proveerá una API capaz de funcionar sin la necesidad de un frontend.
3. La visualización de datos en el frontend deberá ser en forma de listados.
4. El sistema permitirá la creación y administración de bots de Discord.
5. El sistema permitirá la creación y administración de comandos de bots de Discord.
6. Un usuario administrador podrá crear bots de Discord y administrarlos.
7. Los bots contarán con comandos por defecto para conocer el estado de los mismos.

### Requisitos no funcionales

1. El puesto centralizado estará compuesto por un backend, por una serie de workers y un frontend.
2. El frontend tendrá una interfaz sencilla.
3. El sistema funcionará para sistemas basados en GNU Linux.
4. El sistema deberá ser escalable, esto incluye backend, workers y frontend.
5. La interfaz de usuario del sistema será mediante una aplicación web.

### Requisitos de información

1. El sistema almacenará los detalles de los comandos de los bots de Discord.
2. El sistema almacenará los detalles de los bots de Discord que despliega.
3. El sistema almacenará para cada bot un identificador único, un nombre, una key y una lista de comandos.
4. El sistema almacenará para cada comando, un identificador único, un nombre, una lista de argumentos y un atributo que indique el tipo del comando (global o específico).

## Casos de uso

### Usuario de Discord

1. Usar comando.

### Usuario administrador

1. Crear bot
2. Editar bot
3. Eliminar bot
4. Crear comando
5. Editar comando
6. Eliminar comando
7. Agregar comando a bot
8. Eliminar comando de bot
9. Desplegar bot
10. Cancelar despliegue de un bot

## Historias de usuario

Para la creación de las historias de usuarios se ha usado la siguiente estructura.

| Sección                | Significado                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Breve resumen de la historia de usuario.                     |
| Meta                   | Qué se quiere conseguir.                                     |
| Perfil de usuario      | Perfil del usuario que genera la historia de usuario.        |
| Escenario              | Escenario de la historia de usuario. Se deben especificar detalles más concretos.<br />- Dado …<br />- Cuando …<br />- Entonces … |
| Notas funcionales      | Notas adicionales de carácter funcional que ayudan a comprender mejor el alcance de la historia de usuario. |
| Notas técnicas         | Notas adicionales de carácter técnico que ayudan a comprender mejor este tipo de detalles a la hora de desarrollar la historia de usuario. |
| Dependencias           | Posibles dependencias que tenga la historia de usuario. Éstas pueden ser otras historias de usuario, tareas que se estén llevando a cabo, etc. |
| Tareas de seguimiento  | Una vez analizada la historia de usuario, las tareas que se deben realizar a continuación. |
| Criterio de aceptación | Criterio por el cual se va a determinar que la historia de usuario ha sido completada con éxito y por tanto finalizada. |

---

Por otro lado, se han creado las siguientes historias de usuario. Estas se encuentran en el [repositorio de GitHub](https://github.com/harvestcore/matroos) del proyecto, en la sección [*Issues*](https://github.com/harvestcore/matroos/labels/US).

1. [Crear diferentes bots de Discord](https://github.com/harvestcore/matroos/issues/1)
2. [Consultar datos de un bot](https://github.com/harvestcore/matroos/issues/2)
3. [Editar un bot](https://github.com/harvestcore/matroos/issues/3)
4. [Eliminar un bot](https://github.com/harvestcore/matroos/issues/4)
5. [Crear diferentes comandos de Discord](https://github.com/harvestcore/matroos/issues/5)
6. [Consultar datos de un comando](https://github.com/harvestcore/matroos/issues/6)
7. [Editar un comando](https://github.com/harvestcore/matroos/issues/7)
8. [Eliminar un comando](https://github.com/harvestcore/matroos/issues/8)
9. [Lanzar bots de Discord](https://github.com/harvestcore/matroos/issues/9)
10. [Cancelar ejecución de bots](https://github.com/harvestcore/matroos/issues/10)
11. [Consultar estado de los despliegues](https://github.com/harvestcore/matroos/issues/11)
12. [Interfaz de usuario](https://github.com/harvestcore/matroos/issues/25)

---

### 01 - Crear diferentes bots de Discord

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero crear distintos bots de Discord en el sistema para poder configurarlos con los comandos que yo quiera para que éstos realicen las tareas que deseo al ejecutar los comandos en los canales donde he agregado los bots. |
| Meta                   | Creación de bots para que más tarde puedan ser configurados y desplegados y para que puedan ejecutar los comandos configurados en ellos. |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero crear un bot de Discord y configurar sus funcionalidades,<br />- Cuando: proveo al sistema de una KEY de bot de Discord y de un nombre para el bot,<br />- Entonces: el sistema crea un bot para que pueda empezar a configurarlo. |
| Notas funcionales      | - No se debe permitir la creación de bots con el mismo nombre.<br />- No se debe permitir la creación de bots con la misma *key*. |
| Notas técnicas         | Elementos necesarios para la creación del bot:<br />- *key: str [req]*. Key del bot, proporcionada en el panel de control de Discord.<br />- *name: str [req]*. Nombre del bot.<br /><br />Parámetros extra necesarios para crear un bot:<br />- *id: Guid [req]*. Identificador único para cada bot. |
| Dependencias           | –                                                            |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - Los bots se pueden crear correctamente.<br />- El usuario es avisado en caso de error al crear un bot.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 02 - Consultar datos de un bot

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero consultar los detalles de los bots de Discord creados en el sistema, para poder ver sus características y su configuración. |
| Meta                   | Obtener todos los datos de un bot en concreto o de todos los bots creados en el sistema para consultar sus características y configuración. |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero consultar los detalles de los bots creados en el sistema,<br />- Cuando: hago una petición al sistema para ello,<br />- Entonces: el sistema me devuelve los detalles y datos de los bots. |
| Notas funcionales      | - Se debe permitir obtener los detalles de todos los bots.<br />- Se debe permitir obtener los detalles de un bot en específico. |
| Notas técnicas         | Parámetros necesarios para obtener los detalles de un bot específico:<br />- *id: Guid [req]*. Identificador único para cada bot. |
| Dependencias           | –                                                            |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - Todos los datos de los bots son devueltos.<br />- El usuario es avisado en caso de error al obtener los detalles de los bots.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 03 - Editar un bot

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero poder editar los detalles de un bot de Discord, para configurarle comandos nuevos, eliminar existentes o cambiar sus parámetros. |
| Meta                   | Permitir la edición de los parámetros de los bots (comandos, nombre, key, etc). |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero modificar los datos de un bot,<br />- Cuando: proveo al sistema del identificador del bot a editar y los datos que se deben modificar,<br />- Entonces: el sistema modifica los datos del bot. |
| Notas funcionales      | - No se debe permitir la existencia de bots con el mismo nombre.<br />- No se debe permitir la existencia de bots con la misma *key*.<br />- En caso de agregar un comando a un bot, el comando debe estar creado previamente en el sistema.<br />- No se debe permitir la existencia comandos iguales en un mismo bot.<br />- En caso de que el bot se encuentre desplegado, debe reiniciarse el despliegue una vez la edición finaliza. |
| Notas técnicas         | Parámetros necesarios para obtener los detalles de un bot específico y para modificarlo:<br />- *id: Guid [req]*. Identificador único para cada bot.<br />- *key: str*. Key del bot, proporcionada en el panel de control de Discord.<br />- *name: str*. Nombre del bot.<br />- *command_id: Guid*. Identificador único para cada comando. |
| Dependencias           | - HU-01                                                      |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - El bot es modificado correctamente.<br />- El usuario es avisado en caso de error al modificar los datos del bot.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 04 - Eliminar un bot

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero poder eliminar un bot de Discord. |
| Meta                   | Permitir el borrado de bots.                                 |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero eliminar un bot,<br />- Cuando: proveo al sistema del identificador del bot a eliminar,<br />- Entonces: el sistema elimina el bot y sus datos asociados. |
| Notas funcionales      | -  En caso de que el bot se encuentre desplegado, éste despliegue debe cancelarse. |
| Notas técnicas         | Parámetros necesarios para eliminar un bot:<br />- *id: Guid [req]*. Identificador único para cada bot. |
| Dependencias           | - HU-01                                                      |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - El bot es eliminado correctamente.<br />- El usuario es avisado en caso de error al eliminar los datos del bot.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 05 - Crear diferentes comandos de Discord

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero crear distintos comandos para los bots de Discord para que éstos realicen las tareas que deseo tras ejecutarlos en los canales de Discord. |
| Meta                   | Creación de distintos comandos que posteriormente puedan ser asignados a bots. |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero crear un comando de Discord y configurar sus funcionalidades,<br />- Cuando: proveo al sistema de un nombre para el comando y de un prefijo,<br />- Entonces: el sistema crea un comando para que pueda empezar a configurarlo. |
| Notas funcionales      | - No se debe permitir la creación de comandos con el mismo nombre. |
| Notas técnicas         | Elementos necesarios para la creación del comando:<br />- *name: str [req]*. Nombre del comando.<br />- *prefix: str [req]*. Prefijo del comando. |
| Dependencias           | –                                                            |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - Los comandos se crean correctamente.<br />- El usuario es avisado en caso de error al crear un comando.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 06 - Consultar datos de un comando

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero consultar los detalles de los comandos creados en el sistema. |
| Meta                   | Obtener todos los datos de un comando en concreto o de todos los comandos creados en el sistema. |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero consultar los detalles de los comandos creados en el sistema,<br />- Cuando: hago una petición al sistema para ello,<br />- Entonces: el sistema me devuelve los datos de los comandos. |
| Notas funcionales      | - Se debe permitir obtener los detalles de todos los comandos.<br />- Se debe permitir obtener los detalles de un comando en específico. |
| Notas técnicas         | Parámetros necesarios para obtener los detalles de un comando específico:<br />- *id: Guid [req]*. Identificador único para cada comando. |
| Dependencias           | - HU-05                                                      |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - Todos los datos de los comandos son devueltos.<br />- El usuario es avisado en caso de error al obtener los detalles de los comandos.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 07 - Editar un comando

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero poder editar los detalles de un comando para . |
| Meta                   | La edición de los parámetros de los comandos (nombre, prefijo, parámetros, etc). |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero modificar los datos de un comando,<br />- Cuando: proveo al sistema del identificador del comando a editar y los datos que se deben modificar,<br />- Entonces: el sistema modifica los datos del comando. |
| Notas funcionales      | - No se debe permitir la existencia de comandos con el mismo nombre.<br />- En caso de que el comando esté siendo usado por un bot que se encuentre desplegado, este debe ser reiniciado. |
| Notas técnicas         | Parámetros necesarios para obtener los detalles de un bot específico y para modificarlo:<br />- *id: Guid [req]*. Identificador único para cada bot.<br />- *prefix: str*. Prefijo del comando.<br />- *params: dict*. Parámetros adicionales del comando. |
| Dependencias           | - HU-05                                                      |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - El comando es modificado correctamente.<br />- El usuario es avisado en caso de error al modificar los datos del comando.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 08 - Eliminar un comando

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero poder eliminar un comando para que deje de estar disponible en el sistema. |
| Meta                   | El borrado de comandos en el sistema.                        |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero eliminar un comando,<br />- Cuando: proveo al sistema del identificador del comando a eliminar,<br />- Entonces: el sistema elimina el comando y sus datos asociados. |
| Notas funcionales      | - En caso de que el comando esté en uso por un bot desplegado, éste debe reiniciarse. |
| Notas técnicas         | Parámetros necesarios para eliminar un bot:<br />- *id: Guid [req]*. Identificador único para cada bot. |
| Dependencias           | - HU-05                                                      |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - El comando es eliminado correctamente.<br />- El usuario es avisado en caso de error al eliminar los datos del comando.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 09 - Lanzar bots

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero poder ejecutar los bots de Discord que he creado y configurado previamente en el sistema para poder hacer uso de los comandos de los que disponen en los servidores de Discord. |
| Meta                   | Desplegar bots en los workers para que puedan usarse desde los servidores de Discord. |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero desplegar un bot de Discord,<br />- Cuando: proveo al sistema de un identificador de bot de Discord existente,<br />- Entonces: el sistema despliega el bot automáticamente, lo que me permite empezar a hacer uso de sus comandos. |
| Notas funcionales      | - No se debe permitir el despliegue de un bot varias veces.<br />- No se debe permitir el despliegue de un bot que no tiene comandos configurados. |
| Notas técnicas         | Elementos necesarios para el despliegue del bot:<br />- *id: Guid [req]*. Identificador único para cada bot. |
| Dependencias           | - HU-01<br />- HU-03<br />- HU-05<br />- HU-07               |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - El bot queda desplegado correctamente.<br />- El usuario es avisado en caso de error al desplegar un bot.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 10 - Cancelar ejecución de bots

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero terminar la ejecución de un bot de Discord en el sistema para que deje de estar disponible. |
| Meta                   | Terminar la ejecución de bots en los workers para que dejen de poder usarse desde los servidores de Discord. |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero cancelar el despliegue de un bot para realizar algún tipo de tarea de mantenimiento,<br />- Cuando: proveo al sistema de un identificador de bot de Discord que se encuentre desplegado,<br />- Entonces: el sistema termina la ejecución del bot. |
| Notas funcionales      | - No se debe permitir cancelar el despliegue de un bot que no se encuentra desplegado. |
| Notas técnicas         | Parámetros necesarios para cancelar el despliegue de un bot:<br />- *id: Guid [req]*. Identificador único para cada bot. |
| Dependencias           | - HU-01<br />- HU-03<br />- HU-05<br />- HU-07<br />- HU-09  |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - El despliegue del bot es cancelado.<br />- El usuario es avisado en caso de error al cancelar el despliegue del bot.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 11 - Consultar estado de los despliegues

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero conocer el estado de los despliegues de los bots de Discord en el sistema. |
| Meta                   | Obtener detalles de los workers y de los bots que se encuentran desplegados en los workers. |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero conocer el estado de los despliegues de los bots,<br />- Cuando: hago una petición al sistema para ello,<br />- Entonces: el sistema me devuelve los datos de los bots que se encuentran desplegados. |
| Notas funcionales      | - No se deben devolver datos de configuración del bot.<br />- Se debe devolver información de los workers que ejecutan los bots. |
| Notas técnicas         | Datos a devolver:<br />- *workers: []Worker, [req]*. Todos los workers que hay disponibles en el sistema.<br /><br />Worker:<br />- *id: Guid [req]*. Identificador único para cada worker.<br />- *uptime: DateTime*. El tiempo de actividad del worker.<br />- *location: str*. La URL donde se encuentra el worker.<br />- *bots: []Bot*. Los bots que están desplegados en el worker.<br /><br />Bot:<br />- *id: Guid [req]*. Identificador único para cada bot.<br />- *uptime: DateTime*. El tiempo de actividad del bot.<br />- ... |
| Dependencias           | - HU-01<br />- HU-03<br />- HU-05<br />- HU-07<br />- HU-09<br />- HU-10 |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - Los datos de los bots de Discord que se encuentran desplegados son devueltos al usuario.<br />- El usuario es avisado en caso de error al obtener los datos de despliegue.<br />- Tests unitarios y integración son creados dentro de lo posible. |

### 12 - Interfaz de usuario

| Sección                | Contenido                                                    |
| ---------------------- | ------------------------------------------------------------ |
| Resumen                | Como usuario administrador quiero disponer de una interfaz gráfica para poder crear, configurar, desplegar y conocer el estado de los bots de Discord que hay en el sistema. |
| Meta                   | Disponer de una interfaz gráfica que permita realizar las tareas de creación, configuración y despliegue de bots de Discord. |
| Perfil de usuario      | Usuario administrador con conocimientos avanzados en:<br />- Configuración de Discord.<br />- Administración de sistemas.<br />- Despliegue de software y sistemas. |
| Escenario              | - Dado: que quiero administrar los bots de Discord,<br />- Cuando: accedo a la interfaz gráfica,<br />- Entonces: el sistema me permite realizar todas las tareas de administración de bots y comandos. |
| Notas funcionales      | –                                                            |
| Notas técnicas         | –                                                            |
| Dependencias           | - HU-01<br />- HU-02<br />- HU-03<br />- HU-04<br />- HU-05<br />- HU-06<br />- HU-07<br />- HU-08<br />- HU-09<br />- HU-10<br />- HU-11 |
| Tareas de seguimiento  | –                                                            |
| Criterio de aceptación | - La interfaz permite realizar las tareas de gestión de bots y comandos.<br />- El usuario es avisado en caso de producirse algún error.<br />- Tests unitarios y integración son creados dentro de lo posible. |
