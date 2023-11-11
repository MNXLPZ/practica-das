# Selección-Patrón-Mediator

* Status: proposed
* Date: 2023-11-11

## Context and Problem Statement

Se necesita elegir la metodología del patrón a aplicar, dentro del patrón mediator elegiremos entre el estratégico y el simple.

## Decision Drivers

* Se necesita aplicar un patrón mediator a la clase GestorPedidos que hace de intermediario entre los clientes, pedidos, el reparto y las incidencias comunicando dichas funcionalidades.

## Considered Options

* 0009-1-Mediator Estratégico
* 0009-1-Mediator Simple

## Decision Outcome

Chosen option: "0009-1-Mediator Estratégico", because Se adapta mejor a la clase a la que queremos proporcionar la propiedad de mediador. Mediando en la clase Incidencias, se conseguiría gestionar de manera más eficiente el tipo de incidencia, si es para el cliente o es para el repartidor.

### Positive Consequences

* Mayor flexibilidad en los tipos de indicencias.

### Negative Consequences

* Implementación más compleja.

## Pros and Cons of the Options

### 0009-1-Mediator Estratégico

Patrón que actúa de intermediario entre dos o más clases, el estratégico cambia su forma de mediación según el contexto.

* Good, because Mayor flexibilidad, en la mediación.
* Good, because Mejor adaptación a sistemas complejos.
* Bad, because Requiere más esfuerzo de diseño.
* Bad, because Puede ser excesivo para sistemas simples.

### 0009-1-Mediator Simple

Patrón que actúa de intermediario entre dos o más clases, el simple es la versión más clásica y básica.

* Good, because Diseño más sencillo y fácil de entender.
* Good, because Mejor para sistemas poco complejos.
* Good, because Codigo menos extenso.
* Bad, because Dificil de gestionar a medida que el sistema crece.
* Bad, because Puede conducir a acoplamiento directo entre objetos.
