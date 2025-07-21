---
order: 900
label: Buscador natural
icon: /static/icons/products/naturalSearch.svg
---
# ![](/static/icons/products/naturalSearch.svg){width="40"} Buscador natural

El [buscador natural](https://biteral.net/natural-search) permite a vuestros usuarios realizar preguntas, escribir lo que están buscando o describir sus necesidades utilizando lenguaje natural para obtener una lista de los productos que encajan con lo que están buscando.

Como no utilizamos sistemas tradicionales de búsqueda basados en palabras clave, diccionarios, extracción de frecuencia o analizadores sintácticos, los resultados incluyen productos que guardan una relación contextual lógica con la necesidad que el cliente expresó, incluso si no utilizó ninguna de las palabras de la descripción de vuestro producto.

!!!
Como la búsqueda de productos se basa en información conceptualizada, los resultados también incluyen productos relevantes aunque el cliente realice consultas generales, cometa faltas de ortografía o incluso utilice otro idioma.
!!!

### Realizar una búsqueda natural

+++ PHP SDK
Una vez hayas [cargado vuestros productos](/guide/integration-data/products), llama a [!badge variant="info" text="naturalSearch()->query"](/php-sdk/products/add-products) con un objeto [!badge variant="info" text="NaturalSearchQuery"](/php-sdk/entities/natural-search-query) como parámetro:

```php
$products =
    $client->naturalSearch()->query(
        new NaturalSearchQuery(
            query: 'Un regalo para alguien a quien le encanta cocinar'
        )
    );
```

Y obtendrás un array de objetos [!badge variant="info" text="Product"](/php-sdk/entities/product) como resultado:

```php
foreach ($products as $product) {
    echo $product->payload->title."\n";
}
```

+++ API
Una vez hayas [cargado vuestros productos](/guide/integration-data/products), haz una petición [!badge variant="success" text="GET"] al endpoint [!badge /natural-search](/api/endpoints/natural-search/get) pasando la búsqueda en el parámetro [!badge variant="warning" text="query"], por ejemplo: `Un regalo para alguien a quien le encanta cocinar`

Y obtendrás los productos que coinciden así:

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
        "payload": {
            "code": "FNN1848",
            "isActive": true,
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
        "payload": {
            "code": "SJD2818",
            "isActive": true,
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
