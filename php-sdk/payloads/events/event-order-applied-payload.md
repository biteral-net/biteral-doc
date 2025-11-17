---
label: EventOrderAppliedPayload
expanded: false
icon: arrow-right
order: 890
---
{{ include "/snippets/events/descriptions/event-order-applied.md" }}

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="timestamp"]|Datetime|{{ include "/snippets/events/properties/timestamp.md" }}
[!badge variant="danger" icon="lock" text="customerCode"]|string|{{ include "/snippets/events/properties/customer-code.md" }}
[!badge variant="danger" icon="lock" text="orderDescription"]|string|La descripción del orden aplicado. Puede ser cualquier palabra o frase que describa el orden, por ejemplo: `price`, `newest products first`, `screen size`, etcétera.
[!badge icon="screen-full" text="orderDirection"]|string|Si es relevante, la dirección del orden: `asc` para dirección ascendente, `desc` para dirección descendente
