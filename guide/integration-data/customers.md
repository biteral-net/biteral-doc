---
label: Clientes
order: 980
icon: /static/icons/customer.svg
---
# ![](/static/icons/customer.svg){width="40"} Integrar clientes

### Cargar un cliente

+++ PHP SDK

Llama a [!badge variant="info" text="customers()->ingest"](/php-sdk/customers/add-customers) con un objeto [!badge variant="info" text="CustomerPayload"](/php-sdk/payloads/customer-payload) como parámetro:

```php
use Biteral\Entity\Customer\CustomerGender;
use Biteral\Payload\Customer\CustomerPayload;

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
```
+++ API

Haz una petición [!badge variant="success" text="POST"] al endpoint [!badge /customers](/api/endpoints/customers/post) con el JSON body:

```json
{
    "code": "D314K1432",
    "country": "ES",
    "state": "Barcelona",
    "city": "Q11355",
    "yearBorn": 1983,
    "gender": 2,
    "metadata": {
        "currentDiscountRate": "10%",
        "isNew": true
    }
}
```
+++

### Cargar muchos clientes a la vez

+++ PHP SDK
Igual que cuando cargas muchos productos a la vez, puedes cargar varios clientes de forma eficiente utilizando el método de carga masiva de clientes:

[!button icon="arrow-right" variant="info" text="Carga masiva con el SDK"](/php-sdk/customers/add-customers-batch)
+++ API
Puedes cargar varios clientes a la vez pasando un array de clientes a la API, aquí encontrarás los detalles sobre cómo hacerlo:

[!button icon="arrow-right" variant="info" text="Carga masiva con la API"](/api/endpoints/customers/post/#cargar-varios-clientes-a-la-vez)
+++

!!!
Cuando cargas muchos clientes a Biteral muy rápidamente, puede pasar un rato hasta que todos están disponibles para las herramientas de Biteral.
!!!

### Otras operaciones con clientes

+++ PHP SDK
El SDK te permite realizar otras operaciones con clientes, como modificarlos, desactivarlos o eliminarlos.

[!button icon="arrow-right" variant="info" text="Otras operaciones con clientes con el SDK"](/php-sdk/customers/update-customers)
+++ API
La API también te permite realizar otras operaciones con clientes, como modificarlos, desactivarlos o eliminarlos.

[!button icon="arrow-right" variant="info" text="Otras operaciones con clientes con la API"](/api/endpoints/customers/post)
+++
