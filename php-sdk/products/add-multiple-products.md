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

Puedes pasar tantos productos como necesites en el array, aunque es posible que encuentres problemas de memoria si pasas arrays demasiado grandes, dependiendo de la configuración de vuestro servidor.

Internamente los productos siempre se cargan de 100 en 100, así que no obtendrás ningún extra de velocidad con arrays de más de 100 productos.

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
// Obtén todos vuestros productos utilizando vuestros propios métodos,
// de manera que puedas iterar sobre ellos con un bucle while o foreach,
// como en el siguiente ejemplo:
foreach ($products as $product) {

    // Crea un objeto ProductPayload con los datos de vuestro producto,
    // y lo añade al array $productPayloads
    $productPayloads[] =
        new ProductPayload(
            code: $product->getCode(),
            title: $product->getTitle(),
            description: $product->getDescription(),
            price: new PricePayload($product->getPrice(), $product->getCurrency()),
            attributes:
                // Itera sobre todos los atributos de vuestro producto
                // y crea un array donde cada elemento es un objeto
                // ProductAttributePayload
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
