---
label: Product
expanded: false
icon: arrow-right
order: 1000
---
# Product

Representa uno de vuestros productos en Biteral. Además de los datos que habéis proporcionado sobre el producto, incluye información propia de Biteral, como el identificador interno del producto o su estado de procesamiento.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="id"]|string|Id del producto en Biteral. Por ejemplo: `pro_hs14jd193K1ndJ`
[!badge icon="screen-full" text="createdAt"]|int|Fecha de creación del producto. [UNIX timestamp](https://en.wikipedia.org/wiki/Unix_time).
[!badge icon="screen-full" text="updatedAt"]|int|Fecha en la que el producto se actualizó por última vez. [UNIX timestamp](https://en.wikipedia.org/wiki/Unix_time).
[!badge icon="screen-full" text="isActive"]|bool|Indica si este producto está activo en las herramientas de Biteral.
[!badge icon="screen-full" text="payload"]|[!badge variant="info" text="ProductPayload"](/php-sdk/payloads/product-payload)|Payload de los datos del producto
