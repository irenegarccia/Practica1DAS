# Uso del patrón Circuit Breaker para la gestión de pedidos

* Status: proposed
* Date: 2024-11-12

## Context and Problem Statement

Para la funcionalidad de pedidos de productos ofrecidos por la empresa, tenemos los siguientes requisitos funcionales clave:

* RF3: Los clientes podrán realizar pedidos de los productos ofrecidos por la empresa.
* RF3.1: Limitación de intentos al realizar un pedido. El número máximo de intentos que tiene un cliente para realizar un pedido se limitará a 3.
* RF3.2: Preprocesar el pedido. Cuando se realiza un pedido, se verificará la disponibilidad de los productos. Cuando se haya verificado correctamente todo, se autorizará y se aceptará el pedido.
En base a estos requisitos, necesitamos un mecanismo que permita gestionar el número de intentos de manera controlada y que evite la saturación del sistema cuando hay fallos recurrentes o cuando los recursos externos (como la verificación de disponibilidad de productos) no están disponibles temporalmente.

## Decision Drivers

* Implementar el patrón Circuit Breaker para gestionar la funcionalidad de pedidos. El Circuit Breaker controlará los intentos de pedidos y evitará sobrecargar el sistema en caso de fallos reiterados al intentar realizar un pedido o verificar la disponibilidad de productos.

## Considered Options

* Implementar el patrón Circuit Breaker
* Usar un contador de intentos simple sin protección ante fallos externos
* Gestionar manualmente los fallos en cada operación de verificación de disponibilidad y autorización

## Decision Outcome

Chosen option: "Implementar el patrón Circuit Breaker", because el patrón Circuit Breaker nos proporciona las siguientes vetajas:

* Limitación de intentos de manera controlada (RF3.1): El patrón permite gestionar el número de intentos que un cliente puede realizar antes de bloquear el acceso temporalmente, ajustándose a la limitación de 3 intentos requerida.
* Protección contra sobrecarga y fallos recurrentes: Si el sistema externo de verificación de disponibilidad de productos falla de manera continua, el Circuit Breaker interrumpirá temporalmente los intentos, protegiendo el sistema de sobrecargas y mejorando la resiliencia.
* Notificación y Monitoreo: El Circuit Breaker puede configurarse para proporcionar alertas o notificaciones cuando se detectan fallos persistentes, facilitando la identificación de problemas recurrentes en tiempo real.

### Positive Consequences

* Mejora de la Resiliencia: El sistema podrá manejar mejor los fallos de servicios externos sin verse sobrecargado por intentos reiterados.
* Experiencia de Usuario: Los clientes tendrán un sistema más estable, evitando errores recurrentes al realizar pedidos.
* Simplicidad en la Gestión de Errores: El Circuit Breaker facilita la centralización de la lógica de gestión de errores, evitando código duplicado en múltiples partes de la aplicación.

### Negative Consequences

* Complejidad Adicional: Implementar el patrón Circuit Breaker añade cierta complejidad a la arquitectura del sistema, ya que requiere configuración y monitoreo.
* Configuración de Tiempo de Recuperación: Será necesario calibrar los tiempos de recuperación y los umbrales de fallo para evitar bloqueos innecesarios o interrumpir de forma prematura las conexiones.

## Links

* https://keepcoding.io/blog/que-es-el-patron-circuit-breaker/
* https://apiumhub.com/es/tech-blog-barcelona/patron-circuit-breaker/

