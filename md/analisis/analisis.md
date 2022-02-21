# Análisis

## Descripción de actores

- **Administrador**: Crea los bots y los comandos. Tiene poder de configuración y de despliegue. Puede ser también usuario del bot. Agrega los bots a los servidores de Discord. Puede crear otros usuarios administradores.
- **Usuario de Discord**: No realiza ningún tipo de configuración de los bots, comandos o bots. Interactúa con los bots una vez ya han sido configurados y desplegados por un usuario administrador. Hace uso de los comandos configurados en el bot.

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
4. Desplegar bot
5. Cancelar despliegue de un bot
6. Crear comando
7. Editar comando
8. Eliminar comando
9. Agregar comando a bot
10. Eliminar comando de bot

## Modelo de negocio y presupuesto

TBD
