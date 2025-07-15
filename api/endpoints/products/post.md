---
label: Post
order: 100
icon: arrow-right
---
# /products [!badge variant="success" text="POST"] [!badge variant="success" text="v1"]

Crear o modificar un producto.

+++ JSON request body

```json
{
    "code": "N30123",
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
        {"title": "Uso recomendado", "value": "Uso diario y entrenamiento ligero"}
    ],
    "brand": {
        "code": "OW142302",
        "name": "Nike"
    },
    "category": {
        "code": "MC418292",
        "title": "Zapatillas deportivas",
        "description": "Calzado diseñado para ofrecer comodidad, soporte y rendimiento en actividades físicas o deportivas. Estas zapatillas también se adaptan al uso urbano y diario gracias a sus diseños modernos y materiales versátiles. Incluyen características como suelas antideslizantes, tejidos transpirables y estilos que combinan funcionalidad con moda."
    },
    "imageUrl": "https://m.media-amazon.com/images/I/61cELGQXXhL._AC_UL320_.jpg",
    "metadata": {
        "videoUrl": "https://m.media-amazon.com/videos/C/dk14lkKlsnw._AC_UL1080_.mp4",
        "currentDiscountRate": "50%",
        "isNew": true,
        "isFeatured": false
    }
}
```

+++ Documentación

[!badge variant="danger" icon="lock" text="code"]
: Código de producto, por ejemplo `N39291` [!badge variant="light" icon="arrow-both" text="255"]

[!badge variant="danger" icon="lock" text="title"]
: Título del producto. [!badge variant="light" icon="arrow-both" text="10000"]

[!badge variant="warning" text="description"]
: Descripción del producto. [!badge variant="light" icon="arrow-both" text="60000"]

[!badge variant="warning" text="price"]
: El precio del producto. Un objeto JSON donde [!badge variant="danger" icon="lock" text="amount"] es el precio del producto, y [!badge variant="danger" icon="lock" text="currency"] es la moneda en la que se expresa el precio, según el estándar [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217). Por ejemplo:
```json
    {
        "amount": 49.95,
        "currency": "EUR"
    }
```

[!badge variant="warning" text="attributes"]
: Los atributos del producto. Un array de objetos JSON donde [!badge variant="danger" icon="lock" text="title"] [!badge variant="light" icon="arrow-both" text="255"] es el título del atributo y [!badge variant="warning" text="value"] [!badge variant="light" icon="arrow-both" text="60000"] es su valor. Por ejemplo:
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
: La marca del producto. Un objeto JSON donde [!badge variant="danger" icon="lock" text="code"] [!badge variant="light" icon="arrow-both" text="255"] es el código de la marca y [!badge variant="warning" text="name"] [!badge variant="light" icon="arrow-both" text="255"] su nombre. Por ejemplo:
```json
    {
        "code": "OW142398",
        "name": "Nike"
    }
```

[!badge variant="warning" text="category"]
: La categoría del producto. Un objeto JSON donde [!badge variant="danger" icon="lock" text="code"] [!badge variant="light" icon="arrow-both" text="255"] es el código de la categoría, [!badge variant="warning" text="title"] [!badge variant="light" icon="arrow-both" text="255"] el título y [!badge variant="warning" text="description"] [!badge variant="light" icon="arrow-both" text="60000"] su descripción. Por ejemplo:
```json
    {
        "code": "MC418298",
        "title": "Zapatillas deportivas",
        "description": "Calzado diseñado para ofrecer comodidad, soporte y rendimiento en actividades físicas o deportivas. Estas zapatillas también se adaptan al uso urbano y diario gracias a sus diseños modernos y materiales versátiles. Incluyen características como suelas antideslizantes, tejidos transpirables y estilos que combinan funcionalidad con moda."
    }
```

[!badge variant="warning" text="imageUrl"]
: La URL de la imagen del producto, preferiblemente una imagen de aproximadamente 600 píxeles de ancho. Por ejemplo: `https://m.media-amazon.com/images/I/61cELGQXXhL._AC_UL320_.jpg`

[!badge variant="warning" text="metadata"]
: Datos adicionales que te resulten útiles cuando recibas el producto como resultado de las herramientas de Biteral. Un objeto JSON [!badge variant="light" icon="arrow-both" text="60000"]. Por ejemplo:
```json
    {
        "videoUrl": "https://m.media-amazon.com/videos/C/dk14lkKlsnw._AC_UL1080_.mp4",
        "currentDiscountRate": "50%",
        "isNew": true,
        "isFeatured": false
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
        "code": "N30123",
        "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
        "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.",
        "price": {
            "amount": 49.95,
            "currency": "EUR"
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
