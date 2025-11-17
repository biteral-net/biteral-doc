---
label: EventSearchPayload
expanded: false
icon: arrow-right
order: 910
---
{{ include "/snippets/events/descriptions/event-search.md" }}

!!!
Este evento debe enviarse si vuestro web tiene su propio buscador textual. Si utilizáis el buscador natural de Biteral, no es necesario enviar este evento cuando se produce una búsqueda desde allí.
!!!

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="timestamp"]|Datetime|{{ include "/snippets/events/properties/timestamp.md" }}
[!badge variant="danger" icon="lock" text="customerCode"]|string|{{ include "/snippets/events/properties/customer-code.md" }}
[!badge variant="danger" icon="lock" text="query"]|string|El texto de la búsqueda tal como lo escribió el cliente.
