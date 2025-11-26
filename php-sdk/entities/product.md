---
label: Product
expanded: false
icon: arrow-right
order: 1000
---
# Product

Representa uno de vuestros productos en Biteral. Además de los datos que habéis proporcionado sobre el producto, incluye información propia de Biteral, como el identificador interno del producto, la fecha en que se añadió o la fecha de la última actualización.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="id"]|string|Id del producto en Biteral. Por ejemplo: `pro_hs14jd193K1ndJ`
[!badge icon="screen-full" text="projectId"]|string|Id del proyecto en Biteral al que pertenece el producto. Por ejemplo: `prj_18vn8R74uvSijf`
[!badge icon="screen-full" text="createdAt"]|DateTimeImmutable|Fecha de creación del producto.
[!badge icon="screen-full" text="updatedAt"]|DateTimeImmutable|Fecha en la que el producto se actualizó por última vez.
[!badge icon="screen-full" text="payload"]|[!badge variant="info" text="ProductPayload"](/php-sdk/payloads/product-payload)|Payload de los datos del producto
