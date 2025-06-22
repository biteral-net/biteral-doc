---
order: 1000
icon: /static/icons/product.svg
---
# ![](/static/icons/product.svg){width="40"} Productos

Lo más recomendable es comenzar cargando todos los productos disponibles en vuestro e-commerce, para que Biteral pueda empezar a trabajar con ellos. Más adelante podrás actualizar productos individualmente o eliminarlos cuando ya no estén disponibles.

### Cargar un producto

+++ PHP SDK

Llama al método [!badge variant="info" text="products()->post"](/php-sdk/products) pasando un objeto [!badge variant="info" text="Product"] como parámetro:

```php
$product = $client->products()->post(
    new Product(
        code: 'N39291',
        title: 'Zapatillas deportivas urbanas para hombre – modelo AirFlow',
        description: 'Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.',
        price: new Price(45.95, Currency::EURO),
        attributes: [
            new ProductAttribute('Material', 'cuero'),
            new ProductAttribute('Color', 'negro con detalles en gris'),
            new ProductAttribute('Tallas disponibles', '39, 40, 41, 42, 43, 44'),
            new ProductAttribute('Suela', 'goma antideslizante'),
            new ProductAttribute('Peso', '850g (par, talla 42)'),
            new ProductAttribute('Uso recomendado', 'Uso diario y entrenamiento ligero')
        ],
        brand: new ProductBrand('OW142398', 'Nike'),
        category: new ProductCategory('MC418298', 'Zapatillas deportivas')
    )
);
```

Puedes [cargar varios productos a la vez](/php-sdk/products/#cargar-varios-productos-a-la-vez) para que el proceso sea más rápido.

+++ API

Haz una petición [!badge variant="secondary" text="POST"] al endpoint [!badge /products](/api/endpoints/products/post-patch-put) con el JSON body:

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

Puedes [cargar varios productos a la vez](/api/endpoints/products/post-patch-put/#cargar-varios-productos-a-la-vez) para que el proceso sea más rápido.

+++

Es posible que pasen unos minutos hasta que los productos que cargas estén disponibles para las herramientas de Biteral.

!!!secondary
En el [dashboard](https://biteral.net/account/dashboard) podrás ver los productos cargados y el estado del proceso.
!!!

### Calidad de los datos de productos

Cuanta más información precisa, estructurada y actualizada recibimos, mejores son las recomendaciones, análisis y resultados que podemos generar para tu e-commerce. Asegúrate de proporcionar títulos claros, descripciones completas y atributos relevantes.

[!ref Calidad de los datos de productos](/guide/integration-data/products/data-quality)
