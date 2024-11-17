# Implementación del módulo de estadísticas

* Status: proposed
* Date: 2024-11-12

## Context and Problem Statement

Para cumplir con las necesidades del cliente, el sistema debe incluir un módulo de estadísticas que contará con información valiosa sobre diferentes cuestiones del cliente y del pedido. El sistema mostrará información importante del estado del pedido en tiempo real. También, se informará sobre el transporte, mostrando constantemente la ubicación de los camiones, estado y cualquier demora en la entrega. Por último, se ofrecerá las estadísticas de los clientes; incluyendo datos relevantes, como número de pedidos, dinero gastado, etc. Para realizar todo esto en tiempo real, se requiere un sistema escalable y que tenga un rendimiento óptimo.

## Decision Drivers

* RF6-Realizar módulo de estadísticas.
* RF6.1-Estado del pedido.
* RF6.2-Información sobre el transporte.
* RF6.3-Estadísticas de los clientes.

## Considered Options

* Agrupar todas las estadísticas en un mismo módulo
* Agrupar cada tipo de estadística en diferentes módulos

## Decision Outcome

Chosen option: "Agrupar cada tipo de estadística en diferentes módulos", because permitirá una gestión más específica y especializada de la información, para cada área de los distintos tipos de estadísticas (estado del pedido, información del transporte y estadísticas de clientes). Esto permitiría, aumentar la flexibilidad y escalabilidad a cada módulo, pues serán independientes unos de otros. Además, disminuiría la complejidad en el mantenimiento y en la modificación de la información de cada módulo; y permitiría aislar los errores para que un fallo no afecte a todo el módulo de estadísticas.

## Pros and Cons of the Options

### Agrupar todas las estadísticas en un mismo módulo

Implementar un módulo de estadísticas único que gestione e informe sobre el estado del pedido, transporte y estadísticas de clientes.

* Good, because reduce la saturación en la red, mejorando así el rendimiento y eficiencia.
* Good, because todos los datos están centralizados, sin necesidad de que haya comunicaciones entre los distintos tipos de datos.
* Bad, because limita y empeora la flexibilidad, pues para modificar una parte específica de las estadísticas debes modificar todo el conjunto.


### Agrupar cada tipo de estadística en diferentes módulos

Implementar varios módulos y microservicios especificos para cada tipo diferente de estadística.

* Good, because aumenta la flexibilidad, debido a que la escalabilidad a cada módulo es independiente unos de otros, por lo que la modificación de ellos no tiene impacto en el resto.
* Good, because disminuye la complejidad en el mantenimiento y en la modificación de la información de cada módulo.
* Good, because permite aislar los errores e inconvenientes de un tipo de estadística, sin que afecte al resto de módulos.
* Bad, because aumenta la complejidad a la hora de implementarlo en la infraestructura del sistema.
* Bad, because aumenta la sobrecarga en la comunicación, ya que hay datos que tienen relación entre si, provocando retrasos en el sistema.

