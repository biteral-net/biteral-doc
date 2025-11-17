---
label: EventStockAlertRequestedPayload
expanded: false
icon: arrow-right
order: 860
---
{{ include "/snippets/events/descriptions/event-stock-alert-requested.md" }}

!!!
Debe enviarse cuando un cliente solicita ser notificado cuando un producto vuelva a estar disponible para la compra, normalmente, porque encontró el producto pero no estaba disponible para comprar en ese momento debido a falta de stock.
!!!

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="timestamp"]|Datetime|{{ include "/snippets/events/properties/timestamp.md" }}
[!badge variant="danger" icon="lock" text="customerCode"]|string|{{ include "/snippets/events/properties/customer-code.md" }}
[!badge variant="danger" icon="lock" text="productCode"]|string|{{ include "/snippets/events/properties/product-code.md" }}
