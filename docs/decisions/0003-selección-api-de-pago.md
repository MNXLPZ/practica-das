# Selección-API-de-pago

* Status: accepted
* Deciders: Manuel López Corchado y Víctor Candel Casado
* Date: 2023-10-28

## Context and Problem Statement

Se necesita API para conectar los servicios de pago con el cliente.

## Decision Drivers

* •	RF4: Realizar pagos mediante una pasarela externa. Este componente se integrará con una pasarela de pago externa que proporcionará otra empresa.

## Considered Options

* 0003-1-Stripe
* 0003-2-Braintree
* 0003-3-PayPal

## Decision Outcome

Chosen option: "Stripe", because destaca por su flexibilidad y facilidad de integración, lo que hace que sea una opción atractiva para el procesamiento de pagos en línea. Además, ofrece una amplia variedad de métodos de pago y una documentación detallada que facilita la implementación en múltiples plataformas y lenguajes de programación.

### Positive Consequences

* Mayor flexibilidad en la aceptación de métodos de pago.
* Facilidad de integración en múltiples plataformas y lenguajes.
* Documentación detallada para desarrolladores, por lo que se van a optimizar los tiempos de desarrollo.
* Mayor comodidad para los clientes debido a la amplia variedad de opciones de pago.

### Negative Consequences

* Posibilidad de congelación de fondos en ciertas situaciones, que es una desventaja compartida con otras opciones.
* En comparación con PayPal, puede haber tarifas de transacción ligeramente más altas.

## Pros and Cons of the Options

### 0003-1-Stripe

Es una de las pasarelas de pago más populares, conocida por su facilidad de uso y flexibilidad. Ofrecen una API sólida que permite a las empresas procesar pagos en línea.

* Good, because Flexibilidad, permite aceptar una amplia variedad de métodos de pago
* Good, because Facilidad de Integración, la implementación de pagos en línea sea relativamente sencilla y disponile en varios lenguajaes de programación  y plataformas.
* Bad, because Congelación de fondos y pagos en ciertas situaciones

### 0003-2-Braintree

Es una propiedad de PayPal, ofrece una API de pasarela de pago que es popular entre las empresas de comercio electrónico. Es conocida por su soporte para múltiples métodos de pago y su facilidad de integración.

* Good, because Facilidad de Integración, facilitan la integración en aplicaciones y sitios web.
* Good, because Diversidad de Métodos de Pago
* Good, because Escalabilidad, se ajusta a pequeñas y grandes empresas.
* Bad, because Requisito de cuenta de paypal
* Bad, because Congelación de fondos en algunas ocasiones

### 0003-3-PayPal

Ofrece una API que permite a las empresas integrar pagos en sus sitios web y aplicaciones.

* Good, because Amplia Aceptación
* Good, because Soporte global
* Good, because Facilidad de Integración
* Good, because Checkout rápido, que aporta comodidad al cliente
* Bad, because Cuenta de paypal requeridad para los clientes
* Bad, because Tarifas de Transacción altas en comparación con el resto
* Bad, because Congelación de fondos y pagos en ciertas situaciones
