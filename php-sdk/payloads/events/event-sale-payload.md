---
label: EventSalePayload
expanded: false
icon: arrow-right
order: 960
---
{{ include "/snippets/events/descriptions/event-sale.md" }}

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="timestamp"]|Datetime|{{ include "/snippets/events/properties/timestamp.md" }}
[!badge variant="danger" icon="lock" text="customerCode"]|string|{{ include "/snippets/events/properties/customer-code.md" }}
[!badge variant="danger" icon="lock" text="productCode"]|string|{{ include "/snippets/events/properties/product-code.md" }}
[!badge icon="screen-full" text="quantity"]|int|La cantidad de unidades de este producto compradas. Si no se especifica, el valor por defecto es `1`
