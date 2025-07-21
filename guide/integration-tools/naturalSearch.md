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

Una vez hayas [cargado vuestros productos](/guide/integration-data/products), llama al método [!badge variant="info" text="naturalSearch()->query"](/php-sdk/products/add-products) pasando un objeto [!badge variant="info" text="NaturalSearchQuery"](/php-sdk/entities/natural-search-query) como parámetro:

```php
$result = $client->naturalSearch()->query(
    new NaturalSearchQuery(
        query: 'N39291'
    )
);
```
+++ API

Una vez hayas aprendido [cómo conectar con la API](/api/connect), haz una petición [!badge variant="success" text="POST"] al endpoint [!badge /products](/api/endpoints/products/post) con el JSON body:

```json
{
    "code": "N30123",
    "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
    "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.",
    "price": {
        "amount": "49.95",
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
+++
