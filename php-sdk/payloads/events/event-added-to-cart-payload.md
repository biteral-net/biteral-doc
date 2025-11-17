---
label: EventAddedToCartPayload
expanded: false
icon: arrow-right
order: 1000
---
{{ include "/snippets/events/descriptions/event-added-to-cart.md" }}

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="timestamp"]|Datetime|{{ include "/snippets/events/properties/timestamp.md" }}
[!badge variant="danger" icon="lock" text="customerCode"]|string|{{ include "/snippets/events/properties/customer-code.md" }}
[!badge variant="danger" icon="lock" text="productCode"]|string|{{ include "/snippets/events/properties/product-code.md" }}
[!badge icon="screen-full" text="quantity"]|int|La cantidad de unidades de este producto añadidas al carrito. Si no se especifica, el valor por defecto es `1`
