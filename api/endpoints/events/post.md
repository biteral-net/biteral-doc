---
label: Post
order: 100
icon: arrow-right
---
# /events [!badge variant="success" text="POST"] [!badge variant="success" text="v1"]

Enviar un evento.

+++ :icon-project-roadmap: JSON request body

```json
{
    "type": "EventSale",
    "timestamp": "2025-11-18T07:21:16.527Z",
    "customerCode": "D314K1432",
    "productCode": "N30122",
    "quantity": 2
}
```

+++ :icon-book: Documentación

[!badge variant="danger" icon="lock" text="type"]
: Tipo de evento, de entre los [tipos de eventos disponibles](/guide/integration-data/events/types). Por ejemplo `EventAddedToCart`.

[!badge variant="warning" text="timestamp"]
: El momento en el que se produjo el evento. Si no lo especificas, se utilizará el momento actual. Una cadena [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601), por ejemplo: `2025-11-18T07:21:16.527Z`

+++

Recuerda que cada tipo `type` de evento requiere parámetros adicionales diferentes, consulta la guía de eventos disponibles para saber qué parametros debes añadir a cada tipo de evento:

[!ref icon="arrow-right" text="Tipos de eventos disponibles"](/guide/integration-data/events/types)

### Enviar varios eventos a la vez

Si vuestro sistema genera muchos eventos, es mejor enviar los eventos en grupo.

{{ include "/snippets/note_lots_of_events.md" }}

Para enviar eventos en grupo, pasa los eventos en forma de un array, por ejemplo:

```json
[
    {
        "type": "EventSale",
        "timestamp": "2025-11-18T07:21:16.527Z",
        "customerCode": "D314K1432",
        "productCode": "N30122",
        "quantity": 2
    }
    {
        "type": "EventProductViewed",
        "timestamp": "2025-11-18T07:18:13.527Z",
        "customerCode": "D314K1432",
        "productCode": "N30122"
    },
    {
        "type": "EventSearch",
        ...
    },
    ...
]
```

!!!
Puedes cargar hasta 100 eventos a la vez utilizando este método
!!!
