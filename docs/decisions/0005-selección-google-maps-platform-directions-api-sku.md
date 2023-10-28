# Selección-Google-Maps-Platform-Directions-API-SKU

* Status: proposed
* Date: 2023-10-28

## Context and Problem Statement

Dentro de la decisión "0004-selección-api-gestión-reparto" necesitamos decidir que SKU elegir, si la básica o la avanzada

## Decision Drivers

* •	RF4: Realizar pagos mediante una pasarela externa. Este componente se integrará con una pasarela de pago externa que proporcionará otra empresa.

## Considered Options

* 0005-1-SKU: Directions
* 0005-2-SKU: Advanced Directions

## Decision Outcome

Chosen option: "0005-2-SKU: Advanced Directions", because Aunque el precio sea más elevado ofrece más ventajas que la versión básica y consideramos que vale la pena gastar más para optimizar el servicio de entrega, la eficiencia beneficiará a la empresa y será una inversión para el ahorro de tiempo y recursos.

### Positive Consequences

* Rutas más optimizadas y ahorro de tiempo.
* Posibilidad de más entregas por reparto, en cierta parte abarata costes.
* En ubicaciones especiales (hospitales, colegios, etc) se podrá indicar al conductor como llegar correctamente al destino.

### Negative Consequences

* Coste más elevado.

## Pros and Cons of the Options

### 0005-1-SKU: Directions

Servicios básicos de la API Directions.

Precios ($/1000 rutas al mes):
-0-100.000 5$
-100.001-500.000 4$
-500.001+ ?$

* Good, because Lo mencionado en "0004-selección-api-gestión-reparto"
* Good, because Más asequible.
* Bad, because Hasta 10 puntos de parada en cada ruta.
* Bad, because Menos preciso y optimizado.

### 0005-2-SKU: Advanced Directions

Servicios avanzados de la API Directions.

Precios ($/1000 rutas al mes):
-0-100.000 10$
-100.001-500.000 8$
-500.001+ ?$

* Good, because Lo mencionado en "0004-selección-api-gestión-reparto"
* Good, because Más preciso y optimizado.
* Good, because Hasta 25 puntos de parada en cada ruta.
* Good, because Modificadores de ubicación para indicar a los conductores como aproximarse al destino.
* Bad, because Más costoso.
