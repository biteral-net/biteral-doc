---
label: Customer
expanded: false
icon: arrow-right
order: 970
---
# Customer

Representa uno de vuestros clientes en Biteral. Además de los datos que habéis proporcionado sobre el cliente, incluye información propia de Biteral, como el identificador interno del cliente, la fecha en que se añadió o la fecha de la última actualización.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="id"]|string|Id del cliente en Biteral. Por ejemplo: `cus_hs14jd193K1ndJ`
[!badge icon="screen-full" text="projectId"]|string|Id del proyecto en Biteral al que pertenece el cliente. Por ejemplo: `prj_18vn8R74uvSijf`
[!badge icon="screen-full" text="createdAt"]|int|Fecha de creación del cliente. [UNIX timestamp](https://en.wikipedia.org/wiki/Unix_time).
[!badge icon="screen-full" text="updatedAt"]|int|Fecha en la que el cliente se actualizó por última vez. [UNIX timestamp](https://en.wikipedia.org/wiki/Unix_time).
[!badge icon="screen-full" text="payload"]|[!badge variant="info" text="CustomerPayload"](/php-sdk/payloads/customer-payload)|Payload de los datos del cliente
