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
        "title": "Zapatillas deportivas",
        "description": "Calzado diseñado para ofrecer comodidad, soporte y rendimiento en actividades físicas o deportivas. Estas zapatillas también se adaptan al uso urbano y diario gracias a sus diseños modernos y materiales versátiles. Incluyen características como suelas antideslizantes, tejidos transpirables y estilos que combinan funcionalidad con moda."
    }
}
```

+++ Documentación

[!badge variant="danger" icon="lock" text="code"]
: Código de producto, por ejemplo `N39291`

[!badge variant="danger" icon="lock" text="title"]
: Título del producto

[!badge variant="warning" text="description"]
: Descripción del producto.

[!badge variant="warning" text="price"]
: El precio del producto. Un objeto JSON donde [!badge variant="danger" icon="lock" text="amount"] es el precio del producto, y [!badge variant="danger" icon="lock" text="currency"] es la moneda en la que se expresa el precio, según el estándar [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217). Por ejemplo:
```json
    {
        "amount": 49.95,
        "currency": "EUR"
    }
```

[!badge variant="warning" text="attributes"]
: Los atributos del producto. Un array de objetos JSON donde [!badge variant="danger" icon="lock" text="title"] es el título del atributo y [!badge variant="warning" text="value"] es su value. Por ejemplo:
```json
    [
        {"title": "Material", "value": "Cuero"},
        {"title": "Color", "value": "negro con detalles en gris"},
        {"title": "Tallas disponibles", "value": "39, 40, 41, 42, 43, 44"},
        {"title": "Suela", "value": "goma antideslizante"},
        {"title": "Peso", "value": "850g (par, talla 42)"},
        {"title": "Uso recomendado", "value": "Uso diario y entrenamiento ligero"},
    ]
```

[!badge variant="warning" text="brand"]
: La marca del producto. Un objeto JSON donde [!badge variant="danger" icon="lock" text="code"] es el código de la marca y [!badge variant="warning" text="name"] su nombre. Por ejemplo:
```json
    {
        "code": "OW142398",
        "name": "Nike"
    }
```

[!badge variant="warning" text="category"]
: La categoría del producto. Un objeto JSON donde [!badge variant="danger" icon="lock" text="code"] es el código de la categoría, [!badge variant="warning" text="title"] su título y [!badge variant="warning" text="description"] su descripción. Por ejemplo:
```json
    {
        "code": "MC418298",
        "title": "Zapatillas deportivas",
        "description": "Calzado diseñado para ofrecer comodidad, soporte y rendimiento en actividades físicas o deportivas. Estas zapatillas también se adaptan al uso urbano y diario gracias a sus diseños modernos y materiales versátiles. Incluyen características como suelas antideslizantes, tejidos transpirables y estilos que combinan funcionalidad con moda."
    }
```

+++

### Actualizar un producto

Para actualizar los datos sobre un producto, realiza la misma petición `POST` a este endpoint con los nuevos datos. Los datos que no especifiques se eliminarán del producto.

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
            "title": "Zapatillas deportivas",
            "description": "Calzado diseñado para ofrecer comodidad, soporte y rendimiento en actividades físicas o deportivas. Estas zapatillas también se adaptan al uso urbano y diario gracias a sus diseños modernos y materiales versátiles. Incluyen características como suelas antideslizantes, tejidos transpirables y estilos que combinan funcionalidad con moda."
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
