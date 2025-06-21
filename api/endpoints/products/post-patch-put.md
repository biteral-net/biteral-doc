---
label: Post, patch & put
order: 100
icon: chevron-right
---
# /products
[!badge variant="success" text="v1"]

### `POST` Crear un producto

+++ JSON request body

```json
{
    "code": "N39291",
    "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
    "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.",
    "price": {
        "amount": 49.95,
        "currency": "EUR"
    },
    "attributes": [
        {"name": "Material", "value": "Cuero"},
        {"name": "Color", "value": "negro con detalles en gris"},
        {"name": "Tallas disponibles", "value": "39, 40, 41, 42, 43, 44"},
        {"name": "Suela", "value": "goma antideslizante"},
        {"name": "Peso", "value": "850g (par, talla 42)"},
        {"name": "Uso recomendado", "value": "Uso diario y entrenamiento ligero"},
    ],
    "brand": {
        "code": "OW142398",
        "name": "Nike"
    },
    "category": {
        "code": "MC418298",
        "name": "Zapatillas deportivas"
    }
}
```

+++ Documentación

|
--|--
[!badge variant="warning" text="code"]|Código de producto, por ejemplo `N39291` [!badge variant="danger" icon="lock" text="Requerido"]|
[!badge variant="warning" text="title"]|Título del producto [!badge variant="danger" icon="lock" text="Requerido"]
[!badge variant="warning" text="description"]|Descripción del producto.
[!badge variant="warning" text="price"]|El precio del producto, por ejemplo `24.95`
[!badge variant="warning" text="currency"]|La moneda en la que se expresa el precio, según el estándar [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217). Por ejemplo `EUR`
[!badge variant="warning" text="attributes"]|Los atributos del producto
[!badge variant="warning" text="brand"]|La marca del producto
[!badge variant="warning" text="category"]|La categoría del producto

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
        "price": {
            "amount": 49.95,
            "currency": "EUR"
        },
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

### `PATCH` Actualizar un producto

Para actualizar los datos sobre un producto, realiza una petición `PATCH` a este endpoint. Los datos especificados se actualizarán, y los demás permanecerán igual.

### `PUT` Reemplazar un producto

Para reemplazar todos los datos sobre un producto, realiza una petición `PUT`. Los datos que no especifiques se eliminarán del producto.

### Cargar varios productos a la vez

Puedes cargar los productos uno a uno, pero es más rápido cargarlos en bloques. Para hacerlo, pasa los productos en forma de un array, por ejemplo:

```json
[
    {
        "code": "N39291",
        "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
        "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.",
        "price": {
            "amount": 49.95,
            "currency": "EUR"
        },
        "attributes": [
            {"name": "Material", "value": "Cuero"},
            {"name": "Color", "value": "negro con detalles en gris"},
            {"name": "Tallas disponibles", "value": "39, 40, 41, 42, 43, 44"},
            {"name": "Suela", "value": "goma antideslizante"},
            {"name": "Peso", "value": "850g (par, talla 42)"},
            {"name": "Uso recomendado", "value": "Uso diario y entrenamiento ligero"},
        ],
        "brand": {
            "code": "OW142398",
            "name": "Nike"
        },
        "category": {
            "code": "MC418298",
            "name": "Zapatillas deportivas"
        }
    },
    {
        "code" : "J481955"
        ...
    },
    ...
]
```

!!!secondary
Puedes cargar hasta 100 productos a la vez utilizando este método
!!!
