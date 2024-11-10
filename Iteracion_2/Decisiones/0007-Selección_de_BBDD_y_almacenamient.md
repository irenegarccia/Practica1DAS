# Selección-de-BBDD-y-almacenamiento-de-datos

* Status: accepted
* Date: 2024-11-10

## Context and Problem Statement

Para manejar de manera óptima la información de los modulos críticos (Clientes y Pedidos), se busca seleccionar el tipo de base de datos y estructura de almacenamiento de datos más adecuada para gestionar los datos de los diferentes microservicios en el sistema. Tomando esto en cuenta, se ha decidido que la mejor opción es una Base de datos SQL para cada microservicio con diferentes esquemas (Clientes, Pedidos).

## Decision Drivers

* RF2-Acceder a los datos personales de los clientes
* RD1-Base de datos SQL

## Considered Options

* Base de datos SQL única
* Bases de datos SQL independientes

## Decision Outcome

Chosen option: "Bases de datos SQL independientes" para cada microservicio con diferentes esquemas (Clientes, Pedidos).

### Positive Consequences

* Separación clara de datos: Al contar con bases de datos separadas, los datos de Clientes y Pedidos permanecen completamente independientes, lo que mejora la seguridad y la organización.
* Escalabilidad independiente: Cada base de datos puede escalar por separado, lo que optimiza los recursos y permite ajustarse a las necesidades de cada microservicio.
* Mantenimiento simplificado: Las actualizaciones, migraciones o tareas de mantenimiento pueden realizarse en un microservicio sin afectar al otro.

### Negative Consequences

* Costes adicionales: La gestión de bases de datos independientes puede generar mayores costes en infraestructura y administración.
* Complejidad en la integración: La necesidad de mantener la comunicación entre microservicios implica una mayor planificación.

## Pros and Cons of the Options

### Base de datos SQL única

* Bueno, porque supone una menor complejidad en la gestión y menor coste de infraestructura.
* Malo, porque existe el riesgo de tener conflictos de datos y mayor dependencia entre microservicios.

### Bases de datos SQL independientes

* Bueno, porque hay una mayor separación de datos y escalabilidad.
* Malo, porque hay un aumento en los costes y en complejidad para la sincronización de datos entre los servicios.
