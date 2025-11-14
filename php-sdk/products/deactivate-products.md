---
label: Desactivar productos
expanded: false
order: 980
icon: arrow-right
---
# Desactivar productos temporalmente

En algunas ocasiones es posible que necesites desactivar temporalmente algunos productos de forma que no formen parte de los datos que manejan las herramientas de Biteral.

> Por ejemplo, lo más probable es que no desees obtener productos que están **fuera de stock** en los resultados de la búsqueda natural.

En tales casos, pon [!badge icon="screen-full" text="isActive"] en tu producto a `false`:

```php
use Biteral\Payload\Product\ProductPayload;

$productPayload =
    new ProductPayload([
        'code' => 'N39291',
        'isActive' => false
    ]);

$client->products()->ingest($productPayload);
```

Cuando el producto vuelva a estar disponible, reactívalo poniendo [!badge icon="screen-full" text="isActive"] a `true`

!!!
Cuando cargas un producto por primera vez, [!badge icon="screen-full" text="isActive"] será `true` si no especificas lo contrario.
!!!
