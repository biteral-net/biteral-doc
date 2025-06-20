---
label: Delete
order: 60
icon: chevron-right
---
# /products
[!badge variant="success" text="v1"]

### `DELETE` Eliminar un producto

+++ JSON request body

Para localizar un producto a través de su código:

```json
{ "code": "N39291" }
```

Para localizar un producto a través de su id en Biteral:

```json
{ "id": "pro_f28Jfk0i28iXIs" }
```

+++ Documentación

|
--|--
[!badge variant="warning" text="code"]|Código de producto, por ejemplo `N39291`
[!badge variant="warning" text="id"]|Identificador del producto en Biteral, por ejemplo: `pro_f28Jfk0i28iXIs`

+++ Resultado

Este endpoint no devuelve ningún resultado

+++
