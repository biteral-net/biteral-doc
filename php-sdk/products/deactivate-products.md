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
$productPayload =
    new ProductPayload(
        code: 'N39291',
        isActive: false
    );

$client->products()->ingest($productPayload);
```

Cuando el producto vuelva a estar disponible, reactívalo poniendo [!badge icon="screen-full" text="isActive"] a `true`

!!!
Si actualizas los datos de un producto que está desactivado y deseas que siga desactivado, debes volver a enviar explícitamente [!badge icon="screen-full" text="isActive"] como `false` en la petición. Esto se debe a que el valor por defecto de [!badge icon="screen-full" text="isActive"] es `true` cuando no lo especificas en tus peticiones.
!!!
