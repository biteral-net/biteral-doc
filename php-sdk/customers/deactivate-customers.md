---
label: Desactivar clientes
expanded: false
order: 980
icon: arrow-right
---
# Desactivar clientes temporalmente

En algunas ocasiones es posible que necesites desactivar temporalmente algunos clientes de forma que no formen parte de los datos que manejan las herramientas de Biteral.

En tales casos, pon [!badge icon="screen-full" text="isActive"] en tu cliente a `false`:

```php
use Biteral\Payload\Customer\CustomerPayload;

$customerPayload =
    new CustomerPayload([
        'code' => 'D314K1432',
        'isActive' => false
    ]);

$client->customers()->ingest($customerPayload);
```

Cuando el cliente vuelva a estar disponible, reactívalo poniendo [!badge icon="screen-full" text="isActive"] a `true`

!!!
Cuando cargas un cliente por primera vez, [!badge icon="screen-full" text="isActive"] será `true` si no especificas lo contrario.
!!!
