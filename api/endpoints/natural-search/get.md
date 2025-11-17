---
label: Get
order: 70
icon: arrow-right
---
# /natural-search [!badge variant="success" text="GET"] [!badge variant="success" text="v1"]

Obtener una lista de productos que encajan con una búsqueda realizada en lenguage natural.

+++ :icon-tasklist: Parámetros

[!badge variant="danger" icon="lock" text="query"]
: La cadena escrita por el usuario para encontrar productos en lenguaje natural, por ejemplo `Un regalo para un aficionado a la cocina`

[!badge variant="warning" text="limit"]
: Limita el número máximo de productos a obtener, por ejemplo `5`. Por defecto, se obtienen `10` productos como máximo.

+++ :icon-project-roadmap: Resultado

```json
{
    "object": "product",
    "id": "pro_Fj2f4kN1m2dk41",
    "createdAt": "2025-07-02T17:51:50+00:00",
    "updatedAt": null,
    "payload": {
        "code": "DJA8298",
        "isActive": true,
        "title": "Set de regalo para aficionados a la cocina – edición gourmet",
        "description": "Este set de regalo es perfecto para quienes disfrutan cocinando. Incluye una tabla de cortar de bambú, cuchillo de chef profesional de acero inoxidable, delantal personalizado, y un libro de recetas gourmet. Todo presentado en una elegante caja de regalo. Ideal para sorprender a cualquier amante de la cocina con herramientas prácticas y de alta calidad.",
        "attributes": null,
        "brand": null,
        "category": null,
        "price": {
            "amount": "39.90",
            "currency": "EUR"
        }
    },
    {
        "object": "product",
        "id": "pro_Bk3l0gX8m9aj27",
        "createdAt": "2025-07-03T09:22:30+00:00",
        "updatedAt": null,
        "isActive": true,
        "payload": {
            "code": "FNN1848",
            "title": "Kit de especias del mundo – 12 sabores internacionales",
            "description": "Descubre una colección exclusiva de 12 especias seleccionadas de diferentes rincones del mundo. Presentado en frascos de vidrio con etiquetas artesanales, este kit es perfecto para dar un toque especial a cualquier plato y ampliar el repertorio culinario del destinatario.",
            "attributes": null,
            "brand": null,
            "category": null,
            "price": {
                "amount": "29.50",
                "currency": "EUR"
            }
        }
    },
    {
        "object": "product",
        "id": "pro_Yt7q1lRm4xzp90",
        "createdAt": "2025-07-04T14:10:00+00:00",
        "updatedAt": null,
        "isActive": true,
        "payload": {
            "code": "SJD2818",
            "title": "Delantal personalizado con bolsillo – diseño vintage",
            "description": "Un delantal elegante y funcional con diseño vintage, confeccionado en algodón grueso. Cuenta con bolsillo frontal y puede personalizarse con nombre o frase. Un detalle práctico y original para chefs aficionados.",
            "attributes": null,
            "brand": null,
            "category": null,
            "price": {
                "amount": "19.95",
                "currency": "EUR"
            }
        }
    }
}
```

+++
