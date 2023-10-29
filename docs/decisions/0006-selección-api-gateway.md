# Selección-API-Gateway

* Status: accepted
* Deciders: Manuel López Corchado y Víctor Candel Casado
* Date: 2023-10-29

## Context and Problem Statement

Es necesario cambiar el acceso actual por protocolos HTTP/REST mediante un componente Gateway conveniente.

## Decision Drivers

* RF2: Acceder a los datos de la empresa mediante un componente Gateway. Este componente actuará como intermediario entre los clientes y los servicios.

## Considered Options

* 0006-1-Kong Gateway
* 0006-2-APISIX

## Decision Outcome

Chosen option: "0006-2-APISIX", because Tiene un rendimiento superior a sus rivales, además de una comunidad más activa actualmente. Esto junto con su compatibilidad con numerosos lenguajes de programación hacen de esta API la mejor opción.

### Positive Consequences

* Buen rendimiento con latencia mínima, lo que asegura respuestas rápidas.
* Al ser altamente esacable es mejor a la hora del crecimiento empresarial.
* Las características de seguridad y autentificación hacen que la aplicación sea menos vulnerable a ataques.

### Negative Consequences

* Para un uso óptimo de la API hay que ser cuidadoso en la configuración ya que la compatibilidad tan grande que tiene, puede ser un inconveniente si no se implementa de manera correta.

## Pros and Cons of the Options

### 0006-1-Kong Gateway

Gateway de código abierto. Optimizada para la arquitectura de microservicios y construida sobre un proxy liviano, lo que permite minimizar latencia y que sea escalable.

* Good, because Opciones de implementación flexibles, permiten implementarlo localmente, en la nube o como un servicio administrado.
* Good, because Compatibilidad con Lua y Go.
* Good, because El rendimiento satisface las necesidades de la mayoría de usuarios.
* Bad, because Uso predefinido de bases de datos que hacen que la arquitectura esté sobrecargada.
* Bad, because Disminución del rendimiento significativo cuando hay muchas rutas en el gateway.
* Bad, because Algunas funciones importantes son de pago.

### 0006-2-APISIX

Gateway de código abierto. Se basa en NGINX y etcd, se puede integrar con diferentes arquitecturas.

* Good, because Nativo de la nube.
* Good, because Excelente rendimiento (mejor que "Kong Gateway").
* Good, because Ecosistema rico con compatibilidad con numerosos protocolos.
* Good, because Admite complementos de desarrollo en varios lenguajes como java, go, pthon, node, etc.
* Good, because Comunidad muy activa (más que en "Kong Gateway").
* Bad, because Documentación escasa por su salida reciente al mercado.
* Bad, because Para asegurar un funcionamiento óptimo se necesita una supervisión constante.
