---
label: Operar con productos
expanded: false
order: 100
icon: chevron-right
---
# Operar con productos

El SDK para PHP permite cargar productos en Biteral, modificarlos y eliminarlos, además de otras operaciones que te resultarán útiles cuando implementes las herramientas.

### Crear un producto

```php
$product = $client->products()->post(
    new ProductPayload(
        code: 'N39291',
        title: 'Zapatillas deportivas urbanas para hombre – modelo AirFlow',
        description: 'Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.',
        price: 45.95,
        currency: Currency::EURO,
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
    )
);

echo $product->getId();
```

Devuelve un objecto [!badge variant="info" text="Product"](/php-sdk/entities/product)

### Resultado

```
pro_f28Jfk0i28iXIs
```

### Actualización de productos

Cuando los datos de vuestros productos cambien, haz una petición [!badge variant="secondary" text="PATCH"] al endpoint [!badge /products](/api/endpoints/products/post-patch-put) con el código de producto que cambió, y especifica sólo los datos que han cambiado:

```php
$client->products()->patch(
    new Product(
        code: 'N39291',
        title: 'Zapatillas deportivas urbanas unisex – modelo AirFlow',
        price: 48.95
    )
);
```

### Productos fuera de stock

Normalmente no querrás que los productos que están fuera de stock sean tenidos en cuenta por las herramientas de Biteral como, por ejemplo, las recomendaciones personalizadas.

Si es así, cuando un producto esté fuera de stock, haz una petición [!badge variant="secondary" text="PATCH"] al endpoint [!badge /products](/api/endpoints/products/post-patch-put) con el dato [!badge variant="warning" text="isActive"] como `false`:

```php
$client->products()->post(
    new Product(
        code: 'N39291',
        isActive: false
    )
);
```

Cuando el producto vuelva a estar disponible, reactívalo poniendo [!badge variant="warning" text="isActive"] a `true`

### Productos descatalogados

Cuando un producto ya no está a la venta, elimínalo de Biteral haciendo una petición [!badge variant="secondary" text="DELETE"] al endpoint [!badge /products](/api/endpoints/products/delete). Con el SDK para PHP tendría este aspecto:

```php
$client->products()->delete(
    new Product('N39291')
);
```

### Cargar varios productos a la vez

Puedes cargar los productos uno a uno, pero es más rápido cargarlos en bloques. Llama al método [!badge variant="info" text="products()->post"](/php-sdk/products) esta vez pasando un objeto [!badge variant="info" text="ProductsPayload"] como parámetro:

```php
$product = $client->products()->post(
    new ProductsPayload([
        new ProductPayload(
            code: 'N39291',
            title: 'Zapatillas deportivas urbanas para hombre – modelo AirFlow',
            description: 'Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.',
            price: 45.95,
            currency: Currency::EURO,
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
            code: 'N39291',
            title: 'Zapatillas deportivas urbanas para hombre – modelo AirFlow',
            ...
        ),
        ...
    ])
);
```

!!!secondary
Puedes cargar hasta 100 productos a la vez utilizando este método
!!!
