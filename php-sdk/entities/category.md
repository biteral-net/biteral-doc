---
label: Category
expanded: false
icon: arrow-right
order: 990
---
# Category

Representa una de las categorías de vuestros productos en Biteral. Además de los datos que habéis proporcionado sobre la categoría, incluye información propia de Biteral, como el identificador interno de la categoría o su estado de procesamiento.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="id"]|string|Id de la categoría en Biteral. Por ejemplo: `cat_hs14jd193K1ndJ`
[!badge icon="screen-full" text="createdAt"]|DateTimeImmutable|Fecha de creación de la categoría.
[!badge icon="screen-full" text="updatedAt"]|DateTimeImmutable|Fecha en la que la categoría se actualizó por última vez.
[!badge icon="screen-full" text="payload"]|[!badge variant="info" text="CategoryPayload"](/php-sdk/payloads/category-payload)|Payload de los datos de la categoría
