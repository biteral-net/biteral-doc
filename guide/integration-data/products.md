---
label: Productos
order: 1000
icon: /static/icons/product.svg
---
# ![](/static/icons/product.svg){width="40"} Integrar productos

Lo más recomendable es comenzar cargando todos los productos disponibles en vuestro e-commerce para que Biteral pueda empezar a trabajar con ellos, pero primero veamos cómo cargar un único producto:

### Cargar tu primer producto

+++ PHP SDK

Una vez hayas [instalado el SDK](/php-sdk/install), llama al método [!badge variant="info" text="products()->ingest"](/php-sdk/products/add-products) pasando un objeto [!badge variant="info" text="ProductPayload"](/php-sdk/payloads/product-payload) como parámetro:

```php
$product = $client->products()->post(
    new ProductPayload(
        code: 'N39291',
        title: 'Zapatillas deportivas urbanas para hombre – modelo AirFlow',
        description: 'Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.',
        price: new PricePayload(45.95, Currency::EURO),
        attributes: [
            new ProductAttributePayload('Material', 'cuero'),
            new ProductAttributePayload('Color', 'negro con detalles en gris'),
            new ProductAttributePayload('Tallas disponibles', '39, 40, 41, 42, 43, 44'),
            new ProductAttributePayload('Suela', 'goma antideslizante'),
            new ProductAttributePayload('Peso', '850g (par, talla 42)'),
            new ProductAttributePayload('Uso recomendado', 'Uso diario y entrenamiento ligero')
        ],
        brand: new BrandPayload('OW142398', 'Nike'),
        category: new ProductCategoryPayload('MC418298', 'Zapatillas deportivas')
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

### Cargar muchos productos a la vez

Al cargar todo vuestro catálogo, realizar una petición por cada producto sería muy lento. En su lugar, utiliza el método de carga masiva de productos:

+++ PHP SDK
El SDK permite realizar cargas masivas de productos de forma óptima, aquí encontrarás información sobre cómo hacerlo:

[!ref text="Carga masiva con el SDK"](/php-sdk/products/add-products-batch)
+++ API
Puedes cargar varios productos a la vez pasando un array de productos a la API, aquí encontrarás los detalles sobre cómo hacerlo:

[!ref text="Carga masiva con la API"](/api/endpoints/products/post/#cargar-varios-productos-a-la-vez)
+++

!!!
Cuando cargas muchos productos a Biteral muy rápidamente, puede pasar un rato hasta que todos están disponibles para las herramientas de Biteral.
!!!
