# Arquitectura

Se opta por una arquitectura basada en microservicios compuesta por tres servicios distintos:

- **Backend**. Parte principal del sistema. Gestiona la creación de bots y comandos, y el despliegue de los bots. Compuesto por un componente para la gestión de bots, otro para la gestión de comandos, otro de comunicación y finalmente otro de acceso a base de datos.

  ![backend_internals](img/backend_internals.png)

- **Worker**. Ejecuta los bots. Un worker puede ejecutar N bots. Compuesto por un componente para la ejecución de bots y por otro de comunicación.

  ![worker_internals](img/worker_internals.png)

- **Frontend**. Interfaz de usuario. Se comunica con el backend. Compuesto por un componente para la gestión de bots, otro para la gestión de comandos y por otro de comunicación.

  ![frontend_internals](img/frontend_internals.png)

## Backend + workers + frontend

![architecture_with_frontend](img/architecture_with_frontend.png)

## Backend + workers

![architecture_without_frontend](img/architecture_without_frontend.png)

## Autenticación externa + backend + workers + frontend

![auth_with_frontend](img/auth_with_frontend.png)

## Autenticación externa + backend + workers

![auth_without_frontend](img/auth_without_frontend.png)
