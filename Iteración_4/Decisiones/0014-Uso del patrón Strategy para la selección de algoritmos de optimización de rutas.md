# Uso del patrón Strategy para la selección de algoritmos de optimización de rutas

* Status: proposed
* Date: 2024-11-19

## Context and Problem Statement

El sistema debe cumplir con los requisitos funcionales RF5 y RF5.1:  

1. *RF5*: Gestionar rutas de los camiones, optimizando las entregas para maximizar rapidez y eficiencia.  
2. *RF5.1*: Seleccionar dinámicamente entre dos algoritmos de optimización de rutas en función de las circunstancias en tiempo real.  

El problema requiere que el sistema sea capaz de seleccionar y ejecutar el algoritmo más adecuado en tiempo de ejecución, dependiendo de factores como:
- Demora acumulada de los camiones.
- Condiciones de tráfico en tiempo real.
- Distancias y tiempos estimados.

El diseño debe ser modular y fácil de mantener, separando la lógica de selección de los algoritmos de la implementación de los mismos. Esto permitirá incorporar nuevos algoritmos o modificar los existentes sin afectar la funcionalidad central.

## Decision Drivers

* *Requisito funcional RF5*: Garantizar una planificación y optimización eficientes de las rutas.
* *Requisito funcional RF5.1*: Permitir la selección dinámica del algoritmo óptimo en función de datos en tiempo real.

## Considered Options

* ### Option 1: Implementar el patrón Strategy:
* ### Option 2: Lógica de selección dentro del módulo principal de rutas
* ### Option 3: Uso de una biblioteca externa de optimización

## Decision Outcome

Chosen option: "Implementar el patrón Strategy.", because proporciona la mejor solución en términos de flexibilidad, modularidad y escalabilidad, alineándose con los requisitos funcionales RF5 y RF5.1.

## Pros and Cons of the Options

### ### Option 1: Implementar el patrón Strategy:

Separar la lógica de selección y ejecución de algoritmos mediante el patrón Strategy. Cada algoritmo será una clase independiente que implemente una interfaz común (OptimizaciónRutas). Un Context manejará la lógica de selección basándose en los datos proporcionados en tiempo real.

* Good, because Alta modularidad y mantenimiento simplificado.
* Good, because Escalabilidad para agregar o modificar algoritmos sin afectar otras partes del sistema.
* Good, because Cumple perfectamente con RF5 y RF5.1.
* Bad, because Puede agregar un nivel de complejidad en la inicialización de los algoritmos.

### ### Option 2: Lógica de selección dentro del módulo principal de rutas

Mantener toda la lógica de selección y ejecución de algoritmos dentro del módulo principal RepartoYRutasMS.

* Good, because Simplicidad inicial en la implementación.
* Good, because Menos clases y menos código inicial.
* Bad, because Dificultad para escalar y mantener si se agregan nuevos algoritmos.
* Bad, because Mayor acoplamiento entre la lógica de selección y los algoritmos.
* Bad, because No cumple completamente con el requisito de modularidad.

### ### Option 3: Uso de una biblioteca externa de optimización

Integrar una biblioteca de optimización de rutas que permita manejar diferentes algoritmos.

* Good, because Reduce el tiempo de desarrollo inicial.
* Good, because Posible acceso a algoritmos avanzados preimplementados.
* Bad, because Dependencia de un proveedor externo.
* Bad, because Flexibilidad limitada para personalizar la lógica.
* Bad, because Posible impacto en costos.
