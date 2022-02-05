# Introducción

Discord es una herramienta de mensajería de uso tanto personal como en empresas. Además permite la integración de bots, los cuales pueden realizar casi cualquier tipo de función dentro (y fuera) de un servidor.

Actualmente hay dos maneras de crear uno de estos bots, a bajo y alto nivel.

- En el primer caso el bot se crea haciendo uso de las diferentes APIs que ofrece Discord para ello. En este caso la personalización es máxima, ya que lo que se crea está adaptado a las necesidades existentes. En cambio, es más tedioso, y requiere conocimientos extra que algunos usuarios pueden no tener. Además hay que tener en cuenta que el bot debe ser desplegado manualmente, por lo que requiere un esfuerzo extra.
- En el segundo, el bot es creado usando algún tipo de sistema que permite configurar los comandos del mismo. En este caso el bot ya se encuentra desplegado, y los comandos son únicos para cada servidor. Aunque algunos de estos comandos son comunes para todos, los más específicos no se comparten entre servidores. Por otro lado, ya que están pensados para un público general, las posibilidades de configuración son escasas. Suelen tener algunas plantillas de comandos básicos, como temporizadores, respuestas automáticas o incluso música.

Usuarios más avanzados (por ejemplo, un administrador de sistemas, o alguien que controla distintos equipos) que quieren hacer uso de este tipo de tecnologías se ven obligados a crear distintos bots muy específicos y en ocasiones poco reutilizables. Si bien se podrían programar comandos más específicos, sería una tarea tediosa la reutilización entre diferentes proyectos.

Además, en el caso de que se quisieran desplegar distintos bots al mismo tiempo y administrarlos desde un mismo entorno, no sería posible, ya que cada uno de estos es una instancia distinta.

Por tanto, se pretende desarrollar un framework para crear bots de Discord configurables que sean capaces de conectar con diferentes sistemas. La principal motivación a la hora de desarrollar este sistema es encontrar la manera de centralizar la creación y la administración de bots de este tipo, además de resolver los diferentes problemas planteados:

- Dificultad al crear los bots.
- Poca configuración en aspectos más técnicos, como administración de sistemas.
- Dificultad de manejar el despliegue de distintos bots al mismo tiempo.

Es por tanto, un software pensado para usuarios mas avanzados, ya que los usuarios con menor conocimiento de las tareas administrativas sólo hacen uso de estos bots una vez ya desplegados a través de los servidores de Discord.

## Objetivos

El desarrollo de este proyecto tiene los siguientes objetivos:

- Diseñar y programar un sistema compuesto por un frontend, un backend, y una serie de workers que permitan la creación, administración y despliegue de bots de Discord.
- La herramienta permitirá configurar una serie de comandos que facilitan las tareas de administración de sistemas, tales como monitorización, alertas, o tareas en segundo plano.
- Se publicará todo el software creado bajo licencia de software libre.
- El software creado estará disponible en contenedores Docker para facilitar su despliegue y distribución.
- El backend proveerá una API REST que permitirá el desarrollo de distintos frontend y la integración de estos.
- El sistema reducirá el tiempo necesario para crear y desplegar un bot de Discord al menos un 50%.
