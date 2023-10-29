# Selección-patrón-de-base-de-datos

* Status: accepted
* Deciders: Manuel López Corchado y Víctor Candel Casado
* Date: 2023-10-29

## Context and Problem Statement

Es necesario elegir un patrón de bases de datos para enfocarlo a nuestra arquitectura de
microservicios.

## Decision Drivers

* RF1: Migrar la arquitectura monolítica a una basada en microservicios. Este requisito es el
objetivo principal del proyecto y afecta a todos los demás componentes del sistema.
* RF2: Acceder a los datos de la empresa mediante un componente Gateway. Este componente
actuará como intermediario entre los clientes y los servicios.
* RF3: Gestionar el reparto y las rutas de los camiones. Este componente se encargará de asignar
los pedidos a las flotas de transporte, calcular las rutas óptimas de los camiones.
* RF5: Acceder a los datos personales de los clientes. Este componente permitirá consultar y
modificar los datos personales de los clientes.
* RF6: Realizar pedidos de los productos. Este componente permitirá a los clientes realizar
pedidos de los productos disponibles.
* RF7: Reportar incidencias en el reparto. Este componente permitirá reportar a los gestores de
las rutas cualquier tipo de incidencia que ocurra durante el reparto.
* RF8: Proporcionar estadísticas sobre el estado de los pedidos y los camiones. Este componente
proporcionará información valiosa sobre el estado de los pedidos y la situación en tiempo real
de los camiones.

## Considered Options

* 0007-1-CQRS Command Query Responsibility
* 0007-2-Database per Service

## Decision Outcome

Chosen option: "0007-2-Database per Service", because Para cumplir más el aislamiento propio de la arquitectura de microservicios y asegurar la
independencia.

### Positive Consequences

* Fácil evolución independiente de cada microservicio
* Fácil implementación de nuevas funcionalidades.
* La seguridad se ve reforzada por la separación de la información
* Escalabilidad para gestionar grandes cantidades de datos y elevadas cargas de
usuarios

### Negative Consequences

* Más inversión en recursos debido al alto consumo
* Más tiempo y esfuerzo en mantener y evolucionar todo el sistema de bases de datos

* Costes más altos de hardware, licencias de software y personal de mantenimiento

## Pros and Cons of the Options

### 0007-1-CQRS Command Query Responsibility

: Este patrón de diseño separa las
responsabilidades de command y query sobre los datos.

* Good, because Rendimiento y escalabilidad al separar las operaciones de lectura y actualización.
* Good, because Gestión de seguridad más eficaz al separar las operaciones.
* Good, because El sistema es flexible a evoluciones y evita conflictos en el nivel de dominio.
* Bad, because La implementación puede agregar complejidad adicional al sistema.
* Bad, because El aprendizaje de nuevos miembros del equipo sobre este patrón puede ser lento.

### 0007-2-Database per Service

Cada microservicio posee su propia base de datos sin compartirla con ningún otro.

* Good, because Desacoplamiento, cada microservicio es poseedor de su propia base de datos.
* Good, because Permite la reutilización de la lógica de negocio y la separación de responsabilidades.
* Bad, because La separación de las bases de datos puede ser un inconveniente si no se posee de potencia de procesado y memoria en el servidor ya que consume más recursos.
* Bad, because La complejidad de la gestión y mantenimiento de múltiples bases de datos es más alta.
