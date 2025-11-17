---
label: Cargar productos
expanded: false
order: 1000
icon: arrow-right
---
# Cargar productos

El SDK para PHP permite cargar productos en Biteral, modificarlos y eliminarlos, además de otras operaciones que te resultarán útiles cuando implementes las herramientas.

### Cargar un producto

Llama a [!badge variant="light" text="products()->ingest()"] con un objeto [!badge variant="info" text="ProductPayload"](/php-sdk/payloads/product-payload) como parámetro:

```php
use Biteral\Payload\Brand\BrandPayload;
use Biteral\Payload\Shared\PricePayload;
use Biteral\Payload\Product\ProductPayload;
use Biteral\Payload\Product\ProductCategoryPayload;
use Biteral\Payload\Product\ProductAttributePayload;

$productPayload =
    new ProductPayload([
        'code' => 'N30122',
        'title' => 'Zapatillas deportivas urbanas para hombre – modelo AirFlow',
        'description' => 'Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.',
        'attributes' => [
            new ProductAttributePayload(['title' => 'Material', 'value' => 'Cuero']),
            new ProductAttributePayload(['title' => 'Color', 'value' => 'Negro con acentos en gris']),
            new ProductAttributePayload(['title' => 'Tallas disponibles', 'value' => '39, 40, 41, 42, 43, 44']),
            new ProductAttributePayload(['title' => 'Suela', 'value' => 'Goma no-deslizante']),
            new ProductAttributePayload(['title' => 'Peso', 'value' => '850g (par, talla 42)']),
            new ProductAttributePayload(['title' => 'Uso recomendado', 'value' => 'Uso diario y entrenamiento suave'])
        ],
        'brand' => new BrandPayload(['code' => 'OW142302', 'name' => 'Nike']),
        'category' => new ProductCategoryPayload([
            'code' => 'MC418292',
            'title' => 'Zapatillas deportivas',
            'description' => 'Calzado diseñado para proporcionar comodidad, soporte y rendimiento en actividades físicas o deportivas. Estas zapatillas también son adecuadas para el uso urbano y diario gracias a sus diseños modernos y materiales versátiles. Cuentan con suelas antideslizantes, tejidos transpirables y estilos que combinan funcionalidad con moda.'
        ]),
        'price' => new PricePayload(['amount' => '49.95', 'currency' => 'EUR']),
        'imageUrl' => 'https://m.media-amazon.com/images/I/61cELGQXXhL._AC_UL320_.jpg',
        'url' => 'https://www.amazon.es/Hitmars-Zapatillas-Deportivas-Transpirables-Sneakers/dp/B0CYGMZVL7'
    ]);

$client->products()->ingest($productPayload);
```

Esto añadirá el producto a Biteral.

!!!
Ten en cuenta que el producto se añadirá al proyecto que corresponde a la API key que estés utilizando.
!!!
