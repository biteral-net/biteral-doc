---
label: Tipos de eventos
expanded: false
icon: arrow-right
order: 1000
---

==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventAddedToCart**

{{ include "/snippets/events/descriptions/event-added-to-cart.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventAddedToCart"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

[!badge icon="screen-full" text="quantity"]
: La cantidad de unidades de este producto añadidas al carrito. Si no se especifica, el valor por defecto es `1`

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventRemovedFromCart**

{{ include "/snippets/events/descriptions/event-removed-from-cart.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventRemovedFromCart"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

[!badge icon="screen-full" text="quantity"]
: La cantidad de unidades de este producto retiradas del carrito. Si no se especifica, el valor por defecto es `1`

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventAddedToWishlist**

{{ include "/snippets/events/descriptions/event-added-to-wishlist.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventAddedToWishlist"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventRemovedFromWishlist**

{{ include "/snippets/events/descriptions/event-removed-from-wishlist.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventRemovedFromWishlist"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventSale**

{{ include "/snippets/events/descriptions/event-sale.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventSale"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

[!badge icon="screen-full" text="quantity"]
: La cantidad de unidades de este producto compradas. Si no se especifica, el valor por defecto es `1`

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventReturnRequested**

{{ include "/snippets/events/descriptions/event-return-requested.md" }}

!!!
Debe enviarse cuando el cliente solicita la devolución, aunque ésta no sea aceptada, o finalmente no se produzca por cualquier motivo.
!!!

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventReturnRequested"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventProductViewed**

{{ include "/snippets/events/descriptions/event-product-viewed.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventProductViewed"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventCategoryViewed**

{{ include "/snippets/events/descriptions/event-category-viewed.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventCategoryViewed"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="categoryCode"]
: {{ include "/snippets/events/properties/category-code.md" }}

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventBrandViewed**

{{ include "/snippets/events/descriptions/event-brand-viewed.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventBrandViewed"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="brandCode"]
: {{ include "/snippets/events/properties/brand-code.md" }}

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventSearch**

{{ include "/snippets/events/descriptions/event-search.md" }}

!!!
Este evento debe enviarse si vuestro web tiene su propio buscador textual. Si utilizáis el buscador natural de Biteral, no es necesario enviar este evento cuando se produce una búsqueda desde allí.
!!!

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventSearch"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="query"]
: El texto de la búsqueda tal como lo escribió el cliente.

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventFilterApplied**

{{ include "/snippets/events/descriptions/event-filter-applied.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventFilterApplied"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="filterName"]
: El nombre del filtro, por ejemplo: `color`

[!badge variant="danger" icon="lock" text="filterValue"]
: El valor del filtro, por ejemplo: `rojo`

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventOrderApplied**

{{ include "/snippets/events/descriptions/event-order-applied.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventOrderApplied"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="orderDescription"]
: La descripción del orden aplicado. Puede ser cualquier palabra o frase que describa el orden, por ejemplo: `price`, `newest products first`, `screen size`, etcétera.

[!badge icon="screen-full" text="orderDirection"]
: Si es relevante, la dirección del orden: `asc` para dirección ascendente, `desc` para dirección descendente

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventCouponApplied**

{{ include "/snippets/events/descriptions/event-coupon-applied.md" }}

!!!
Debe enviarse sólo cuando el código del cupón introducido por el cliente haya sido confirmado como válido.
!!!

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventCouponApplied"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventReviewWritten**

{{ include "/snippets/events/descriptions/event-review-written.md" }}

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventReviewWritten"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

[!badge icon="screen-full" text="review"]
: El texto de la review, tal como la escribió el cliente.

==-


==- **![](/static/icons/event.svg){.custom-icon}{width="18"} EventStockAlertRequested**

{{ include "/snippets/events/descriptions/event-stock-alert-requested.md" }}

!!!
Debe enviarse cuando un cliente solicita ser notificado cuando un producto vuelva a estar disponible para la compra, normalmente, porque encontró el producto pero no estaba disponible para comprar en ese momento debido a falta de stock.
!!!

##### Parámetros

[!badge variant="danger" icon="lock" text="type"]
: [!badge variant="warning" text="EventStockAlertRequested"]

[!badge icon="screen-full" text="timestamp"]
: {{ include "/snippets/events/properties/timestamp.md" }}

[!badge variant="danger" icon="lock" text="customerCode"]
: {{ include "/snippets/events/properties/customer-code.md" }}

[!badge variant="danger" icon="lock" text="productCode"]
: {{ include "/snippets/events/properties/product-code.md" }}

[!badge icon="screen-full" text="review"]
: El texto de la review, tal como la escribió el cliente.

==-