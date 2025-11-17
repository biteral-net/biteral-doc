---
label: EventReviewWrittenPayload
expanded: false
icon: arrow-right
order: 870
---
{{ include "/snippets/events/descriptions/event-review-written.md" }}

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="timestamp"]|Datetime|{{ include "/snippets/events/properties/timestamp.md" }}
[!badge variant="danger" icon="lock" text="customerCode"]|string|{{ include "/snippets/events/properties/customer-code.md" }}
[!badge variant="danger" icon="lock" text="productCode"]|string|{{ include "/snippets/events/properties/product-code.md" }}
[!badge icon="screen-full" text="review"]|string|El texto de la review, tal como la escribió el cliente.
