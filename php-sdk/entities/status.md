---
label: Status
expanded: false
icon: arrow-right
order: 1100
---
# Status

Representa el estado actual de la API de Biteral, y además proporciona información sobre tu petición, tus credenciales y otros datos útiles como las versiones de API disponibles, o la versión que estás actualizando actualmente.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="id"]|string|Id del producto en Biteral. Por ejemplo: `pro_hs14jd193K1ndJ`
[!badge icon="screen-full" text="createdAt"]|int|Fecha de creación del producto. [UNIX timestamp](https://en.wikipedia.org/wiki/Unix_time).
[!badge icon="screen-full" text="updatedAt"]|int|Fecha en la que el producto se actualizó por última vez. [UNIX timestamp](https://en.wikipedia.org/wiki/Unix_time).
[!badge icon="screen-full" text="payload"]|[!badge variant="info" text="ProductPayload"](/php-sdk/payloads/product-payload)|Payload de los datos del producto
