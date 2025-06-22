---
label: Get
order: 70
icon: arrow-right
---
# /products
[!badge variant="success" text="v1"]

### `GET` Obtener un producto

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

```json
{
    "entity": "Product",
    "id": "pro_f28Jfk0i28iXIs",
    "data": {
        "code": "N39291",
        "isActive": true,
        "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
        "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.",
        "price": 49.95,
        "currency": "EUR",
        "attributes": [
            {"entity": "ProductAttribute", "name": "Material", "value": "Cuero"},
            {"entity": "ProductAttribute", "name": "Color", "value": "negro con detalles en gris"},
            {"entity": "ProductAttribute", "name": "Tallas disponibles", "value": "39, 40, 41, 42, 43, 44"},
            {"entity": "ProductAttribute", "name": "Suela", "value": "goma antideslizante"},
            {"entity": "ProductAttribute", "name": "Peso", "value": "850g (par, talla 42)"},
            {"entity": "ProductAttribute", "name": "Uso recomendado", "value": "Uso diario y entrenamiento ligero"},
        ],
        "brand": {
            "entity": "Brand",
            "id": "pbr_fja9AiaijfaKf",
            "code": "OW142398",
            "name": "Nike"
        },
        "category": {
            "entity": "ProductCategory",
            "id": "pca_19FAkfaqcmz0f",
            "code": "MC418298",
            "name": "Zapatillas deportivas"
        }
    },
    "processingStatus": "ready",
    "createdAt": "2025-06-20T15:29:51+00:00",
    "updatedAt": "2025-06-21T12:33:02+00:00",
    "readyAt": "2025-06-21T12:33:08+00:00"
}
```

+++
