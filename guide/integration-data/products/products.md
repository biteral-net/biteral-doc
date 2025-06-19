---
order: 1000
icon: /static/icons/product.svg
---
# ![](/static/icons/product.svg){width="40"} Productos

Para empezar, realiza un envío masivo de todos los productos que están a la venta para que Biteral pueda empezar a trabajar. Más adelante podrás actualizar productos individualmente, o eliminarlos cuando ya no estén disponibles.

Puedes hacer peticiones a la API directamente, o utilizar el [SDK de Biteral para PHP](/php-sdk).

[!ref Cómo realizar peticiones a la API](/api/intro)

#### Enviar un producto con la API

Haz una petición [!badge variant="secondary" text="POST"] al endpoint [!badge /products](/api/endpoints/products/post). Si utilizas el SDK para PHP, tendría este aspecto:

```php
$client->products()->post(
    new Product(
        code: 'N39291',
        title: 'Zapatillas deportivas urbanas para hombre – modelo AirFlow',
        description: 'Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.',
        brand: 'Nike',
        attributes: [
            new ProductAttribute('Material', 'cuero'),
            new ProductAttribute('Color', 'negro con detalles en gris'),
            new ProductAttribute('Tallas disponibles', '39, 40, 41, 42, 43, 44'),
            new ProductAttribute('Suela', 'goma antideslizante'),
            new ProductAttribute('Peso', '850g (par, talla 42)'),
            new ProductAttribute('Uso recomendado', 'uso diario y entrenamiento ligero')
        ],
        price: 45.95,
        currency: Currency::EURO
    )
);
```

Es posible que pasen unos minutos hasta que los productos que cargas estén disponibles para las herramientas de Biteral.

!!!secondary
En el [dashboard](https://biteral.net/account/dashboard) podrás ver los productos cargados y el estado del proceso.
!!!

#### Calidad de los datos de productos

Cuanta más información precisa, estructurada y actualizada recibimos, mejores son las recomendaciones, análisis y resultados que podemos generar para tu e-commerce. Asegúrate de proporcionar títulos claros, descripciones completas y atributos relevantes.

[!ref Calidad de los datos de productos](/guide/integration-data/products/data-quality.md)

#### Actualización de productos

Cuando los datos de vuestros productos cambien, haz una petición [!badge variant="secondary" text="PATCH"] al endpoint [!badge /products](/api/endpoints/products/patch) con el código de producto que cambió, y especifica sólo los datos que han cambiado:

```php
$client->products()->patch(
    new Product(
        code: 'N39291',
        title: 'Zapatillas deportivas urbanas unisex – modelo AirFlow',
        price: 48.95
    )
);
```

#### Productos fuera de stock

Normalmente no querrás que los productos que están fuera de stock sean tenidos en cuenta por las herramientas de Biteral como, por ejemplo, las recomendaciones personalizadas.

Si es así, cuando un producto esté fuera de stock, haz una petición [!badge variant="secondary" text="PATCH"] al endpoint [!badge /products](/api/endpoints/products/post) con el dato [!badge variant="warning" text="isActive"] como `false`:

```php
$client->products()->post(
    new Product(
        code: 'N39291',
        isActive: false
    )
);
```

Cuando el producto vuelva a estar disponible, reactívalo poniendo [!badge variant="warning" text="isActive"] a `true`

#### Productos descatalogados

Cuando un producto ya no está a la venta, elimínalo de Biteral haciendo una petición [!badge variant="secondary" text="DELETE"] al endpoint [!badge /products](/api/endpoints/products/delete). Con el SDK para PHP tendría este aspecto:

```php
$client->products()->delete(
    new Product('N39291')
);
```
