# Selección-API-Gestión-Reparto

* Status: accepted
* Deciders: Manuel López Corchado y Víctor Candel Casado
* Date: 2023-10-28

## Context and Problem Statement

Se necesita de una API de gestión de reparto para organizar la entrega a domicilio de repartos, dicha API deberá sevir a los conductores mediante un GPS

## Decision Drivers

* •	RF4: Realizar pagos mediante una pasarela externa. Este componente se integrará con una pasarela de pago externa que proporcionará otra empresa.

## Considered Options

* 0004-1-Google Maps Platform, Directions API
* 0004-2-Here Location Services, Routing API
* 0004-3-MapBox, Directions API

## Decision Outcome

Chosen option: "0004-1-Google Maps Platform, Directions API", because Estimación de tiempos y distancias precisa, se puede implementar tanto en web como en móvil, es multiplataforma. La documentación es extensa al igual que el soporte.

### Positive Consequences

* Mayor precisión a la hora de dar plazos de tiempo al cliente.
* Más adaptabilidad en la integración en dispositivos eléctricos.
* Posibilidad de integrar servicios adicionales para combinarlos.

### Negative Consequences

* Precios más altos.
* Complejidad de mantenimiento.
* En un futuro podría encarecerse el servicio afectando a la empresa directamente.

## Pros and Cons of the Options

### 0004-1-Google Maps Platform, Directions API

Muy conocida. Devuelve direcciones entre ubicaciones en formato JSON o XML.

* Good, because Amplia cobertura geográfica, extensa base de datos de ubicaciones de todo el mundo que facilitan la navegación en cualquier lugar.
* Good, because Actualizaciones del tráfico en tiempo real, ajuste de rutas automático.
* Good, because Combinable con otras soluciones de Google para mejorar el sevicio.
* Bad, because A más rutas más será el coste del servicio.
* Bad, because La configuración de la API y la gestión de la clave pueden ser complicadas.
* Bad, because Puede que cambien su política de precios, perjudicando el servicio y el beneficio de la empresa.

### 0004-2-Here Location Services, Routing API

Ofrece instrucciones en 108 idiomas y una optimización de la ruta con más de 100 parámetros.

Precios ($/1000 rutas al mes):
-0-30.000 0$
-30.001-5.000.000 0.830$
-5.000.001-10.000.000 0.660$
-10M+ ?$

* Good, because Optimización de rutas avanzada, optimiza las paradas de la ruta.
* Good, because Geocodificación precisa, ubicación precisa de las direcciones de entrega.
* Good, because Visualización de mapas personalizados, opciones útiles para conductores o información adicional.
* Good, because Personalización, posibilidad de estética corporativa.
* Good, because Asequible.
* Bad, because Complejidad de configuración inicial.
* Bad, because La optimización de rutas puede llevar tiempo.
* Bad, because Menos conocida y utilizada, comunidad y recursos en línea más escasos.
* Bad, because Servicios extra aplicables a la API bastante caros.

### 0004-3-MapBox, Directions API

Devuelve una ruta óptima con duraciones, distancias e instrucciones precisas.

Precios ($/usuario)
-0-100u 0$
-101-20.000u 0.30$
Precios ($/1000 rutas al mes):
-0-1.000r 0$
-1.001-50.000r 0.08$
-50.001-100.000r 0.064$
-100.001-200.000r 0.048$
-200.001+r ?$

* Good, because Flexibilidad estética de diseño de mapas.
* Good, because Datos de tráfico en tiempo real, redirección basada en el tráfico para una ruta más rápida.
* Good, because Integrable en dispositivos móviles.
* Good, because Asequible.
* Bad, because Limitaciones de cobertura geográfica.
* Bad, because Menos datos del tráfico.
* Bad, because Menos opciones de personalización que Routing API.
