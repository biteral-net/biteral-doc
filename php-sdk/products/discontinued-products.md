---
label: Descatalogados
expanded: false
order: 970
icon: arrow-right
---
# Productos descatalogados

Cuando un producto ya no está a la venta, elimínalo de Biteral con el método [!badge variant="light" text="products()->deleteByCode()"], que te permite eliminar un producto a través de vuestro código de producto:

```php
$client->products()->deleteByCode('N39291');
```

También puedes utilizar [!badge variant="light" text="products()->deleteById()"], que te permitie eliminar un producto utilizando su id en Biteral.
