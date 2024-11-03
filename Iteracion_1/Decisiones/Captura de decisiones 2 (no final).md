# Componentes y separación de módulos

* Status: pending.
* Date: 2024-10-31

## Context and Problem Statement

Para mejorar la organización y el rendimiento del sistema, se ha considerado necesario dividir los módulos según su criticidad. Esta estrategia busca implementar cada módulo como un microservicio, permitiendo una gestión más eficaz y escalable.

1.	Decisión: Dividir los módulos según su criticidad (Clientes, Pedidos, Reparto y Rutas, Estadísticas, Incidencias y Pagos) para implementar cada uno como microservicio.

2.	Razonamiento: Optimizar la escalabilidad y gestión de cada componente, especialmente aquellos con mayores requisitos de seguridad y disponibilidad, como Clientes y Pagos.

3.	Opción elegida: Desacoplar cada módulo en su propio microservicio con API REST para la comunicación.


## Decision Drivers

* RF1-Cambio de arquitectura
* RF2-Acceder a los datos personales de los clientes
* RF3-Realizar pedidos de los productos de la empresa
* RF4-Gestionar el reparto de flotas de transporte a los clientes y las rutas de los camiones
* RF5-Gestionar ruta de los camiones
* RF6-Realizar módulo de estadísticas
* RF7-Reportar incidencias
* RF9-Realizar pago
* RF10-Gestionar pedidos



## Decision Outcome

La decisión de dividir los módulos en microservicios permite no solo una mayor escalabilidad, sino también un mejor manejo de la seguridad y disponibilidad de los servicios críticos. Al implementar APIs REST, se logra una comunicación eficiente entre los diferentes componentes del sistema, favoreciendo su independencia y facilitando futuros desarrollos.

### Positive Consequences

* Escalabilidad: Permite escalar cada módulo de forma independiente y por ello optimizamos la escalabilidad del sistema.
* Mantenimiento: Facilita el mantenimiento y la actualización de módulos sin afectar al sistema en su totalidad.
* Seguridad: Mejora la gestión de cada componente, especialmente aquellos con mayor nivel de seguridad al permitir configuraciones específicas para cada microservicio crítico.

### Negative Consequences

* Complejidad: Puede aumentar la complejidad del sistema al tener múltiples microservicios que gestionar.
* Comunicaciones: Aumenta la sobrecarga de comunicación entre los microservicios, lo que puede impactar el rendimiento si no se gestiona adecuadamente.

 
