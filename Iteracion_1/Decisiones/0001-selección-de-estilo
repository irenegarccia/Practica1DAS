# Selección-del-estilo

* Status: accepted
* Date: 2024-11-05

## Context and Problem Statement

Para desarrollar la migración correcta, se ha considerado que la mejor opción es adoptar una arquitectura cliente-servidor en tres capas (presentación, lógica de negocio y acceso a datos) usando microservicios para desacoplar módulos críticos.

## Decision Drivers

* RF1-Cambio de arquitectura

## Considered Options

* Estilo por capas
* REST
* Cliente-Servidor

## Decision Outcome

Chosen option: "Cliente-Servidor", because se considera que es la arquitectura más adecuada para soportar una migración hacia microservicios. Esta estructura permite una separación clara entre la capa de presentación, la lógica de negocio y el acceso a datos, lo que facilita la implementación de microservicios para cada componente crítico (Clientes, Pedidos, Reparto y rutas, Incidencias, Pagos).

### Positive Consequences

* Escalabilidad y Flexibilidad: Facilita el despliegue de cada módulo como un servicio independiente, mejorando la escalabilidad.
* Facilidad de Mantenimiento: Permite realizar cambios en un módulo sin afectar a otros, lo que es ideal para un sistema modular y distribuido.
* Compatibilidad con Microservicios: La estructura en tres capas es idónea para migrar hacia una arquitectura de microservicios.

### Negative Consequences

* Complejidad Inicial: Puede aumentar la complejidad en la configuración y el despliegue de la infraestructura de microservicios.
* Sobrecarga de Comunicación: El modelo cliente-servidor en tres capas puede aumentar la carga de comunicación entre servicios en comparación con una arquitectura monolítica.

## Pros and Cons of the Options

### Estilo por capas

Escalabilidad y Flexibilidad: Facilita el despliegue de cada módulo como un servicio independiente, mejorando la escalabilidad.

* Good, because fomenta una organización clara del código, separando la presentación, la lógica de negocio y el acceso a datos, lo que facilita el desarrollo y la comprensión del sistema.
* Good, because permite la reutilización de componentes dentro de cada capa, reduciendo la duplicación de código y mejorando la modularidad.
* Good, because simplifica el mantenimiento al aislar las responsabilidades; cada capa se centra en una función específica.
* Bad, because añade latencia, ya que cada solicitud debe pasar por varias capas, afectando potencialmente el rendimiento.
* Bad, because genera acoplamiento entre capas, lo cual puede dificultar los cambios en una capa sin afectar a las demás.
* Bad, because tiene una escalabilidad limitada, ya que escalar una capa específica sin las otras puede ser complejo y menos eficiente.
* Bad, because requiere un esfuerzo de mantenimiento adicional; incluso pequeños cambios pueden afectar a múltiples capas y exigir ajustes en cada una.

### REST

Un estilo arquitectónico que facilita el acceso a recursos, pero que puede ser menos intuitivo en arquitecturas cliente-servidor con tres capas definidas.

* Good, because cumple con los requisitos de acceso y manipulación de recursos de la aplicación.
* Bad, because requiere desarrollar un servicio web, lo cual puede implicar una mayor inversión en seguridad y gestión de estados.

### Cliente-Servidor

Esta opción facilita la transición hacia microservicios, segmentando en presentación, lógica y datos.

* Good, because facilita el desarrollo modular y la independencia de cada servicio.
* Good, because aumenta la flexibilidad y escalabilidad del sistema.
* Bad, because porque puede incrementar la carga de comunicación y configuración entre capas en un entorno distribuido.
