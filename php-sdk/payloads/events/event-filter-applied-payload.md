---
label: EventFilterAppliedPayload
expanded: false
icon: arrow-right
order: 900
---
{{ include "/snippets/events/descriptions/event-filter-applied.md" }}

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="timestamp"]|Datetime|{{ include "/snippets/events/properties/timestamp.md" }}
[!badge variant="danger" icon="lock" text="customerCode"]|string|{{ include "/snippets/events/properties/customer-code.md" }}
[!badge variant="danger" icon="lock" text="filterName"]|string|El nombre del filtro, por ejemplo: `color`
[!badge variant="danger" icon="lock" text="filterValue"]|string|El valor del filtro, por ejemplo: `rojo`
