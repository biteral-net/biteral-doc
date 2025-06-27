---
label: Post
order: 100
icon: arrow-right
---
# /products
[!badge variant="success" text="v1"]

### `POST` Crear o modificar un producto

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
        {"title": "Material", "value": "Cuero"},
        {"title": "Color", "value": "negro con detalles en gris"},
        {"title": "Tallas disponibles", "value": "39, 40, 41, 42, 43, 44"},
        {"title": "Suela", "value": "goma antideslizante"},
        {"title": "Peso", "value": "850g (par, talla 42)"},
        {"title": "Uso recomendado", "value": "Uso diario y entrenamiento ligero"},
    ],
    "brand": {
        "code": "OW142398",
        "name": "Nike"
    },
    "category": {
        "code": "MC418298",
        "title": "Zapatillas deportivas"
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

+++

### Actualizar un producto

Para actualizar los datos sobre un producto, realiza la misma `POST` a este endpoint con los nuevos datos. Los datos que no especifiques se eliminarán del producto.

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
            {"title": "Material", "value": "Cuero"},
            {"title": "Color", "value": "negro con detalles en gris"},
            {"title": "Tallas disponibles", "value": "39, 40, 41, 42, 43, 44"},
            {"title": "Suela", "value": "goma antideslizante"},
            {"title": "Peso", "value": "850g (par, talla 42)"},
            {"title": "Uso recomendado", "value": "Uso diario y entrenamiento ligero"},
        ],
        "brand": {
            "code": "OW142398",
            "name": "Nike"
        },
        "category": {
            "code": "MC418298",
            "title": "Zapatillas deportivas"
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
