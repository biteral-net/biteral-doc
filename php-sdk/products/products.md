---
label: Operar con productos
expanded: false
order: 100
icon: arrow-right
---
# Operar con productos

El SDK para PHP permite cargar productos en Biteral, modificarlos y eliminarlos, además de otras operaciones que te resultarán útiles cuando implementes las herramientas.

### Crear un producto

Llama a [!badge variant="light" text="products()->ingest()"] pasando un objeto [!badge variant="info" text="ProductPayload"](/php-sdk/payloads/product-payload) como parámetro:

```php
$productPayload =
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
    );

$client->products()->ingest($productPayload);
```

Esto añadirá el producto a Biteral. Ten en cuenta que el producto se añadirá al proyecto que corresponde a la API key que estés utilizando.

### Actualización de productos

Para cambiar los datos de un producto que ya cargaste, llama a [!badge variant="light" text="products()->ingest()"] igual que cuando lo creaste arriba. Esta vez puedes especificar tan sólo los datos que cambiaron, aunque puedes enviar todos los demás datos de nuevo si te resulta más cómodo:

```php
$productPayload =
    new ProductPayload(
        code: 'N39291',
        price: new PricePayload(49.95, Currency::EURO)
    );

$client->products()->ingest($productPayload);
```

Al actualizar productos, es imprescindible especificar al menos [!badge icon="screen-full" text="code"]

> Si los datos que envías al actualizar un producto no contienen ningún cambio respecto a los valores actuales, no se considera una actualización. En ese caso, la petición `ingest` no cuenta para tu cuota de peticiones `ingest` facturables.

### Desactivar productos temporalmente

En algunas ocasiones es posible que necesites desactivar temporalmente algunos productos de forma que no formen parte de los datos que manejan las herramientas de Biteral.

> Por ejemplo, lo más probable es que no desees obtener productos que están **fuera de stock** en los resultados de la búsqueda natural.

En tales casos, pon [!badge icon="screen-full" text="isActive"] en tu producto a `false`:

```php
$productPayload =
    new ProductPayload(
        code: 'N39291',
        isActive: false
    );

$client->products()->ingest($productPayload);
```

Cuando el producto vuelva a estar disponible, reactívalo poniendo [!badge icon="screen-full" text="isActive"] a `true`

> Si actualizas los datos de un producto que está desactivado y deseas que siga desactivado, debes volver a enviar explícitamente [!badge icon="screen-full" text="isActive"] como `false` en la petición. Esto se debe a que el valor por defecto de [!badge icon="screen-full" text="isActive"] es `true` cuando no lo especificas en tus peticiones.

### Productos descatalogados

Cuando un producto ya no está a la venta, elimínalo de Biteral con el método [!badge variant="light" text="products()->deleteByCode()"], que te permite eliminar un producto a través de vuestro código de producto:

```php
$client->products()->deleteByCode('N39291');
```

También puedes utilizar [!badge variant="light" text="products()->deleteById()"], que te permitie eliminar un producto utilizando su id en Biteral.
