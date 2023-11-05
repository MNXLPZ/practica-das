# Selección-Patrón-Notificaciones

* Status: proposed
* Date: 2023-11-05

## Context and Problem Statement

Se necesita que a los usuarios les lleguen notificaciones de la aplicación. Pueden ser respecto a su pedido, que se han publicado nuevos productos, etcétera.

## Decision Drivers

* RF8 : Proporcionar estadisticas sobre el estado de los pedidos y los camiones.

## Considered Options

* 0008-1-Patrón Observer
* 0008-2-Patrón Publicador-Suscriptor

## Decision Outcome

Chosen option: "0008-2-Patrón Publicador-Suscriptor", because Es un patrón más desacoplado, su personalización hacia el usuario hace que sea atractivo personalizando notificaciones para los intereses comunes a cada usuario, estos intereses pueden ser averiguados mediante cookies, estadísticas de compra, etc.

### Positive Consequences

* Mayor satisfacción de usuario al poderse enfocar mejor las notificaciones.
* Es conveniente para actividades en tiempo real, permite recibir eventos casi en el acto.
* Se podrán agregar y desagregar "etiquetas" de manera modularizada.

### Negative Consequences

* La implementación puede ser compleja.
* Los eventos se pueden perder si no hay suscriptores en el momento de la publicación.
* Se necesitan estadísticas para enfocar mejor las "etiquetas".

## Pros and Cons of the Options

### 0008-1-Patrón Observer

Patrón en el que un objeto sujeto mantiene a una lista de otros objetos llamados observadores y los notifica de cualquier cambio de estado.

* Good, because Modularidad, los nuevos observadores se agregan sin modificar el código existente.
* Good, because Los observadores se pueden utilizar en diferentes contextos ya que no dependen del sujeto observable.
* Bad, because Los observadores se agregan y retiran de manera explícita.
* Bad, because Emite notificaciones que pueden no ser de importancia para todos los observadores.

### 0008-2-Patrón Publicador-Suscriptor

Patrón en el que los publicadores categorizan mensajes que son recibidos por los suscriptores a los que les corresponde cada categoría.

* Good, because Poco acoplamiento, publicador y suscriptor no necesitan información del otro. Pueden evolucionar de manera independiente.
* Good, because Alta escalabilidad.
* Bad, because El testing puede llegar a ser muy complicado si hay muchos tipos de "etiquetas".
* Bad, because Se debe gestionar bien la memoria para evitar colapsos y cuellos de botella en el bus de eventos.
