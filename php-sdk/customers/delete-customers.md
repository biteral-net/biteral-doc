---
label: Eliminar clientes
expanded: false
order: 970
icon: arrow-right
---
# Eliminar clientes

Cuando un cliente deja de serlo, es mejor eliminarlo también de Biteral para asegurarte de que no se utilizan recursos en Biteral para datos que ya están obsoletos. Elimínalo de Biteral con el método [!badge variant="light" text="customers()->deleteByCode()"]:

```php
$client->customers()->deleteByCode('D314K1432');
```

También puedes utilizar [!badge variant="light" text="customers()->deleteById()"], que te permitie eliminar un cliente utilizando su id en Biteral.
