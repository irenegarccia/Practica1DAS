# Operativa de pagos

* Status: accepted
* Date: 2024-11-10

## Context and Problem Statement

Se implementará un módulo de pagos seguro para permitir a los clientes realizar pagos mediante una pasarela externa. Este módulo debe asegurar la compatibilidad con diferentes tipos de clientes y cumplir con altos estándares de seguridad en las transacciones, usando la pasarela de pago externa de Stripe.

Dado que el componente de pagos es clasificado como crítico para la operación, su implementación debe garantizar una mínima exposición de datos sensibles y una adecuada integración con el resto de la arquitectura de microservicios.

## Decision Drivers

* RF8 Realizar pago
* RD2 Pasarela de pago externa

## Decision Outcome

Chosen option: "Implementar un módulo de pago seguro y compatible con otros clientes, que permita el acceso a la pasarela de pago externa de Stripe.", because proporciona una solución segura y escalable con numerosos beneficios, especialmente en términos de seguridad, mantenimiento y experiencia de usuario.

### Positive Consequences

* Bueno, porque mejora la seguridad de los pagos al almacenar los datos de pago externamente y cumplir con los estándares de la industria.
* Bueno, porque mejora la escalabilidad, permitiendo una mayor flexibilidad para el crecimiento en el número de pedidos y clientes.
* Bueno, porque reduce la carga de mantenimiento de seguridad en el sistema, ya que las actualizaciones y mejoras de seguridad son gestionadas directamente por el proveedor de pagos.
* Bueno, porque ofrece un flujo de pago optimizado para diferentes dispositivos, mejorando la experiencia del cliente.

### Negative Consequences

* Malo, porque el sistema queda vinculado a las políticas, tarifas y disponibilidad de un tercero. Esto puede afectar la flexibilidad y generar costes adicionales.
* Malo, porque implica adaptarse a la interfaz y flujo de usuario definidos por la pasarela externa de pago.
* Malo, porque en caso de problemas de red o caídas de Stripe, el sistema de pagos podría no estar disponible, afectando directamente la experiencia de usuario y la capacidad de completar pedidos.
