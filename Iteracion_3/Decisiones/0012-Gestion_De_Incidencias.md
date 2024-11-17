# Gestión de Incidencias

* Status: proposed
* Date: 2024-11-12

## Context and Problem Statement

Se busca implementar un sistema eficiente que permita recibir notificaciones en tiempo real sobre problemas que puedan afectar la entrega de pedidos, como averías de camiones o repartos fallidos. Dado que estas incidencias impactan directamente en la logística y satisfacción del cliente, se requiere un mecanismo ágil y autónomo que capture, notifique y permita resolver problemas sin afectar otros módulos de la arquitectura de distribución. Al ser un modulo crítico, se busca asegurar tanto eficiencia, minimizando el tiempo de respuesta y maximizando la capacidad para resolver problemas, como escalabilidad, para soportar un gran número de incidencias, dado el potencial crecimiento del sistema.

## Decision Drivers

* RF7 Gestionar incidencias

## Decision Outcome

Chosen option: "Diseñar el módulo de gestión de incidencias como un microservicio autónomo que permita la gestión de notificaciones y seguimiento de problemas en el proceso de reparto", because permite desacoplar esta función del módulo de reparto y rutas, facilitando un mantenimiento independiente y escalabilidad según las necesidades del sistema. Este diseño permite a los gestores de rutas recibir notificaciones en tiempo real sobre problemas en la entrega de pedidos y asegurando la visibilidad continua y la rápida respuesta ante problemas con los repartos.

### Positive Consequences

* Mejora la respuesta en tiempo real y permite escalabilidad independiente.
* Facilita la observabilidad de incidencias y notificaciones mediante monitoreo separado.
* Proporciona flexibilidad para añadir nuevas notificaciones de incidencias.

### Negative Consequences

* Incremento en la complejidad de la arquitectura al añadir un microservicio adicional.
* Dependencia en infraestructura adicional para mensajería de eventos.
* Necesidad de asegurar una comunicación confiable con otros módulos como Reparto y Rutas.
