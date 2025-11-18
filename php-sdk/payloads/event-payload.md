---
label: EventPayload
expanded: false
icon: arrow-right
order: 960
---
# EventPayload

Representa un evento ocurrido en vuestro sistema. Por ejemplo, una venta realizada.

### Propiedades principales

||
---|---|---
[!badge icon="screen-full" text="type"]|string|El nombre del tipo de evento, de entre los [tipos de eventos disponibles](/guide/integration-data/events/types). Por ejemplo: `EventAddedToCart`
[!badge icon="screen-full" text="timestamp"]|DateTimeImmutable|El momento en el que se produjo el evento. Si no lo especificas, se utilizará el momento actual.

!!!warning
Cada tipo `type` de evento requiere algunas propiedades adicionales. Consulta los [tipos de eventos disponibles y sus propiedades adicionales](/guide/integration-data/events/types).
!!!