---
label: Get
order: 70
icon: arrow-right
---
# /products [!badge variant="success" text="GET"] [!badge variant="success" text="v1"]

Obtener un producto.

+++ :icon-tasklist: Parámetros

Especifica uno de estos dos parámetros para obtener un producto a través de su código o de su Id en Biteral:

[!badge variant="warning" text="code"]
: Código de producto, por ejemplo `N39291`

[!badge variant="warning" text="id"]
: Identificador del producto en Biteral, por ejemplo: `pro_f28Jfk0i28iXIs`

+++ :icon-project-roadmap: Resultado

```json
{
    "object": "product",
    "id": "pro_T743ujEHOI3Fz4",
    "createdAt": "2025-07-02T17:51:50+00:00",
    "updatedAt": null,
    "payload": {
        "code": "N30122",
        "isActive": true,
        "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
        "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.",
        "attributes": [
            {
                "object": "product_attribute",
                "id": "att_emMDUSQtOUH7Ms",
                "createdAt": "2025-07-02T17:51:50+00:00",
                "updatedAt": null,
                "payload": {
                    "title": "Material",
                    "value": "Cuero"
                }
            },
            {
                "object": "product_attribute",
                "id": "att_gXRdrp7X3XMA1l",
                "createdAt": "2025-07-02T17:51:50+00:00",
                "updatedAt": null,
                "payload": {
                    "title": "Color",
                    "value": "negro con detalles en gris"
                }
            },
            {
                "object": "product_attribute",
                "id": "att_lIVqsz91O5QzYc",
                "createdAt": "2025-07-02T17:51:50+00:00",
                "updatedAt": null,
                "payload": {
                    "title": "Suela",
                    "value": "goma antideslizante"
                }
            },
            {
                "object": "product_attribute",
                "id": "att_qbOmTRs9pEbOll",
                "createdAt": "2025-07-02T17:51:50+00:00",
                "updatedAt": null,
                "payload": {
                    "title": "Uso recomendado",
                    "value": "Uso diario y entrenamiento ligero"
                }
            },
            {
                "object": "product_attribute",
                "id": "att_qN9PKSTG7mhyI5",
                "createdAt": "2025-07-02T17:51:50+00:00",
                "updatedAt": null,
                "payload": {
                    "title": "Tallas disponibles",
                    "value": "39, 40, 41, 42, 43, 44"
                }
            },
            {
                "object": "product_attribute",
                "id": "att_xFON2UUYKQYMLg",
                "createdAt": "2025-07-02T17:51:50+00:00",
                "updatedAt": null,
                "payload": {
                    "title": "Peso",
                    "value": "850g (par, talla 42)"
                }
            }
        ],
        "brand": {
            "object": "product_brand",
            "id": "bra_npTCsTj4PCvziZ",
            "createdAt": "2025-07-02T17:51:50+00:00",
            "updatedAt": null,
            "payload": {
                "code": "OW142302",
                "name": "Nike"
            }
        },
        "category": {
            "object": "product_category",
            "id": "cat_QLEPkCAVbYFELo",
            "createdAt": "2025-07-02T17:51:50+00:00",
            "updatedAt": null,
            "payload": {
                "code": "MC418292",
                "title": "Zapatillas deportivas",
                "description": "Calzado diseñado para ofrecer comodidad, soporte y rendimiento en actividades físicas o deportivas. Estas zapatillas también se adaptan al uso urbano y diario gracias a sus diseños modernos y materiales versátiles. Incluyen características como suelas antideslizantes, tejidos transpirables y estilos que combinan funcionalidad con moda."
            }
        },
        "price": {
            "amount": "49.95",
            "currency": "EUR"
        },
        "imageUrl": "https://m.media-amazon.com/images/I/61cELGQXXhL._AC_UL320_.jpg",
        "url": "https://www.amazon.es/Hitmars-Zapatillas-Deportivas-Transpirables-Sneakers/dp/B0CYGMZVL7",
        "metadata": {
            "videoUrl": "https://m.media-amazon.com/videos/C/dk14lkKlsnw._AC_UL1080_.mp4",
            "currentDiscountRate": "50%",
            "isNew": true,
            "isFeatured": false
        }
    }
}
```

+++
