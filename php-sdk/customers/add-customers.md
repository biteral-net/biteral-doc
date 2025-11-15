---
label: Cargar clientes
expanded: false
order: 1000
icon: arrow-right
---
# Cargar clientes

El SDK para PHP permite cargar clientes en Biteral, modificarlos y eliminarlos, además de otras operaciones que te resultarán útiles cuando implementes las herramientas.

### Crear un cliente

Llama a [!badge variant="light" text="customers()->ingest()"] con un objeto [!badge variant="info" text="CustomerPayload"](/php-sdk/payloads/customer-payload) como parámetro:

```php
use Biteral\Entity\Customer\CustomerGender;
use Biteral\Payload\Customer\CustomerPayload;

$client = new Client($apiKey, $apiVersion, $apiBaseUrl);

$customerPayload =
    new CustomerPayload([
        'code' => 'D314K1432',
        'country' => 'ES',
        'state' => 'Barcelona',
        'city' => 'Q11355',
        'yearBorn' => 1983,
        'gender' => CustomerGender::FEMALE,
        'metadata' => [
            'currentDiscountRate' => '10%',
            'isNew' => true
        ]
    ]);

$client->customers()->ingest($customerPayload);
```

Esto añadirá el cliente a Biteral.

!!!
Ten en cuenta que el cliente se añadirá al proyecto que corresponde a la API key que estés utilizando.
!!!
