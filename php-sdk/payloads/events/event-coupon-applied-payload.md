---
label: EventCouponAppliedPayload
expanded: false
icon: arrow-right
order: 880
---
{{ include "/snippets/events/descriptions/event-coupon-applied.md" }}

!!!
Debe enviarse sólo cuando el código del cupón introducido por el cliente haya sido confirmado como válido.
!!!

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="timestamp"]|Datetime|{{ include "/snippets/events/properties/timestamp.md" }}
[!badge variant="danger" icon="lock" text="customerCode"]|string|{{ include "/snippets/events/properties/customer-code.md" }}
