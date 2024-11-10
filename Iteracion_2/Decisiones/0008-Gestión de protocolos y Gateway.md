# Gestión de Protocolos y Gateway

* Status: accepted.
* Date: 2024-11-10.

## Context and Problem Statement

Con el fin de optimizar la interacción de los clientes externos y mejorar la seguridad en el acceso a los servicios del sistema, se ha considerado la implementación de un API Gateway. Este componente permitirá gestionar de manera eficiente las solicitudes HTTP/REST provenientes de diferentes clientes, incluidas aplicaciones móviles.

1.	Decisión: Utilizar un API Gateway para gestionar las solicitudes HTTP/REST de clientes y móviles.

2.	Razonamiento: Facilitar y centralizar el acceso desde clientes externos y mejorar la seguridad del sistema.

3.	Opción elegida: Implementar un componente Gateway para gestionar el acceso externo y la comunicación.

## Decision Drivers

* RF1.1-Protocolo HTTP/REST

## Decision Outcome

Chosen option: "Implementar un API Gateway", because permitirá una mejor gestión de las solicitudes de los clientes, asegurando un acceso centralizado y controlado a los diferentes microservicios del sistema. Esto contribuirá a mejorar la seguridad al servir como un punto de control para la autenticación y autorización

### Positive Consequences

* Centralización: Proporciona un punto único de acceso para todas las solicitudes, simplificando la arquitectura del sistema.
* Seguridad Mejorada: Facilita la implementación de políticas de seguridad, como autenticación y autorización, en un solo lugar.
* Flexibilidad: Permite la adaptación de las solicitudes y respuestas a diferentes formatos, optimizando la comunicación con los clientes.

### Negative Consequences

* Punto Único de Fallo: Si el API Gateway falla, puede interrumpir el acceso a todos los servicios, lo que exige una gestión cuidadosa de la disponibilidad.
* Sobrecarga de Comunicación: Puede incrementar la latencia debido a la intermediación en la comunicación entre clientes y servicios backend.
