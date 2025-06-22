---
label: Carga masiva
expanded: false
order: 100
icon: arrow-right
---
# Carga masiva de productos

Puedes cargar los productos uno a uno, pero es más rápido cargarlos en bloques. Llama al método [!badge variant="info" text="products()->post"](/php-sdk/products), pero esta vez pasando un array de objetos [!badge variant="info" text="ProductPayload"](/php-sdk/payloads/product-payload) como parámetro:

```php
$product = $client->products()->post(
    [
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
            brand: new ProductBrandPayload('OW142398', 'Nike'),
            category: new ProductCategoryPayload('MC418298', 'Zapatillas deportivas')
        ),
        new ProductPayload(
            code: 'J481955',
            ...
        ),
        ...
    ]
);
```

!!!secondary
Puedes cargar hasta 100 productos a la vez utilizando este método
!!!

Aquí tienes un pequeño snippet que puedes utilizar como referencia para cargar todos vuestros productos en Biteral rápidamente:

```php
use Biteral\Client;
use Biteral\Payload\ProductPayload;
use Biteral\Payload\PricePayload;
use Biteral\Payload\ProductAttributePayload;
use Biteral\Payload\ProductBrandPayload;
use Biteral\Payload\ProductCategoryPayload;

$client = new Client('ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ');

$productPayloads = [];
/* Obtén todos vuestros productos utilizando vuestros propios métodos,
de forma que puedas hacer un bucle while o foreach que itere sobre
todos vuestros productos, como éste: */
foreach ($products as $product) {

    // Crea un objeto ProductPayload con los datos de vuestro producto, y lo añade al array $productPayloads
    $productPayloads[] =
        new ProductPayload(
            code: $product->getCode(),
            title: $product->getTitle(),
            description: $product->getDescription(),
            price: new PricePayload($product->getPrice(), $product->getCurrency()),
            attributes:
                // Itera sobre todos los atributos de vuestro producto y crea un array donde cada elemento es un objeto ProductAttributePayload
                array_map(
                    fn ($attribute) =>
                        new ProductAttributePayload($attribute->getName(), $attribute->getValue()),
                    $product->getAttributes()
                ),
            brand: new ProductBrandPayload($product->getBrand()->getCode(), $product->getBrand()->getName()),
            category: new ProductCategoryPayload($product->getCategory()->getCode(), $product->getCategory()->getTitle())
        );

    // Si ya hay 100 productos en el array, los envía a Biteral
    if (count($productPayloads) === 100) {
        $client->products()->post($productPayloads);
        $productPayloads = [];
    }
}

// Si aún quedan productos en el array, los envía a Biteral
if (!empty($productPayloads)) {
    $client->products()->post($productPayloads);
}
```
