# Selección-Estilo-Arquitectura

* Status: accepted
* Deciders: Manuel López Corchado y Víctor Candel Casado
* Date: 2023-10-21

## Context and Problem Statement

Se necesita encontrar una arquitectura de software que sea lo más compatible posible con una aplicación de una compañía de productos que permita gestionar clientes, pedidos, reparto y rutas, estadísticas, indicencias y pagos.

## Decision Drivers

* •	RF1: Migrar la arquitectura monolítica a una basada en microservicios. Este requisito es el objetivo principal del proyecto y afecta a todos los demás componentes del sistema.
* •	RF2: Acceder a los datos de la empresa mediante un componente Gateway. Este componente actuará como intermediario entre los clientes y los servicios.
* •	RF3: Gestionar el reparto y las rutas de los camiones. Este componente se encargará de asignar los pedidos a las flotas de transporte, calcular las rutas óptimas de los camiones.
* •	RF4: Realizar pagos mediante una pasarela externa. Este componente se integrará con una pasarela de pago externa que proporcionará otra empresa.
* •	RF5: Acceder a los datos personales de los clientes. Este componente permitirá consultar y modificar los datos personales de los clientes.
* •	RF6: Realizar pedidos de los productos. Este componente permitirá a los clientes realizar pedidos de los productos disponibles.
* •	RF7: Reportar incidencias en el reparto. Este componente permitirá reportar a los gestores de las rutas cualquier tipo de incidencia que ocurra durante el reparto.
* •	RF8: Proporcionar estadísticas sobre el estado de los pedidos y los camiones. Este componente proporcionará información valiosa sobre el estado de los pedidos y la situación en tiempo real de los camiones.

## Considered Options

* 0002-1-Arquitectura-Microservicios
* 0002-2-Arquitectura monolítica
* 0002-3-Arquitectura Orientada a Servicios
* 0002-4-Arquitectura por capas

## Decision Outcome

Chosen option: "0002-1-Arquitectura-Microservicios", because Teniendo en cuenta los requerimientos del cliente y las decisiones internas del grupo de desarrollo, la arquitectura de microservicios brinda más ventajas que las demás, las desventajas que posee las consideramos asumibles.

### Positive Consequences

* Más modularidad, cada microservicio puede ajustarse sin afectar a los demás.
* Mejora de funcionamiento, si un microservicio falla, no afecta al resto.
* Escalabilidad mejorada al poderse replicar e integrar cada microservicio con facilidad.

### Negative Consequences

* La complejidad aumenta al gestionar múltiples servicios.
* Costes de implementación y mantenimiento mayores.
* Es menos eficiente que la arquitectura actualmente implementada (monolítica).

## Pros and Cons of the Options

### 0002-1-Arquitectura-Microservicios

Divide una aplicación en servicios pequeños e independientes que se comunican a través de APIs.

* Good, because Escalabilidad.
* Good, because Modularidad.
* Good, because Código reutilizable.
* Good, because Agilidad en cambios.
* Good, because Aplicación independiente.
* Good, because Menor riesgo.
* Bad, because Alto consumo de memoria.
* Bad, because Dificultad en la realización de pruebas.
* Bad, because Gestión complicada por el número de componentes.
* Bad, because Aislamiento, dificulta la depuración.
* Bad, because Coste de implantación alto.

### 0002-2-Arquitectura monolítica

Es una arquitectura simple y fácil de construir.

* Good, because Simplicidad.
* Good, because Despliegue sencillo.
* Good, because Seguridad.
* Bad, because Escalabilidad limitada, ineficiente al crecer.
* Bad, because Dependencia del servidor.

### 0002-3-Arquitectura Orientada a Servicios

Permite la integración de sistemas a través de servicios independientes y reutilizables que se comunican entre sí.

* Good, because Reutilización de los componentes.
* Good, because Agilidad empresarial.
* Bad, because Vulnerable a ataques basados en HTML y XML.
* Bad, because Gran consumo de recursos.

### 0002-4-Arquitectura por capas

Separación de diferentes funcionalidades del sistema en capas o niveles.

* Good, because Separación clara de responsabilidades.
* Good, because Simplicidad.
* Good, because Bajo coste.
* Bad, because Cambios pueden requerir desplegar todas las capas.
* Bad, because Bajo rendimiento y escalabilidad complicada.
* Bad, because Trabajo redundante entre capas
