# Implementación del Reparto de Flotas

* Status: proposed.
* Date: 2024-11-19.

## Context and Problem Statement

Para cumplir con las necesidades del cliente, el sistema debe gestionar la asignación de las flotas de transporte a los distintos clientes. El sistema está unido con la clase de pedidos, lo que permite que, cuando se realice un pedido, se solicite una flota, y se asigne un camión disponible para la entrega de un pedido específico en una ruta determinada.Además, Se requiere un sistema eficiente y óptimo para la gestión de flotas, y con una integración fluida.

## Decision Drivers

* RF4-Gestionar el reparto de flotas de transporte a los clientes.

## Decision Outcome

Chosen option: "Implementar una clase centralizada de gestión de flotas", because permite realizar una gestión eficiente del reparto de flotas de transporte y facilita la integración en el sistema con las clases de Pedidos y Rutas.

### Positive Consequences

* Good, because facilita la integración con otras clases, como Pedidos y Rutas.
* Good, because permite realizar una gestión eficiente del reparto de flotas, al ser una clase centralizada.



### Negative Consequences

* Bad, because limita la flexibilidad ya que no depende de si misma, sino que depende de las comunicaciones que realiza con pedido.
