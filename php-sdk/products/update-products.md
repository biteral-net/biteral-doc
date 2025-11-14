---
label: Actualizar productos
expanded: false
order: 990
icon: arrow-right
---
Para cambiar los datos de un producto que ya cargaste, llama a [!badge variant="light" text="products()->ingest()"] nuevamente, pero esta vez especifica sólo los datos que cambian. También puedes especificar los demás datos si te resulta más cómodo, aunque no hayan cambiado.

```php
use Biteral\Payload\Product\ProductPayload;

$productPayload =
    new ProductPayload([
        'code' => 'N39291',
        'price' => new PricePayload(['amount' => '39.90', 'currency' => 'EUR'])
    ]);

$client->products()->ingest($productPayload);
```

Al actualizar productos, es imprescindible especificar al menos [!badge icon="screen-full" text="code"]

!!!
Si quieres eliminar un dato de un producto, establece su valor a `null`
!!!


!!!
Si los datos que envías al actualizar un producto no contienen ningún cambio respecto a los valores actuales, no se considera una actualización. En ese caso, la petición `ingest` no cuenta para tu cuota de peticiones `ingest` facturables.
!!!
