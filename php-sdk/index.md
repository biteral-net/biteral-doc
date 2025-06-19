---
label: PHP SDK
icon: file-code
expanded: false
order: 80
---
# PHP SDK

El SDK de Biteral PHP es un package para composer que te permite integrar con facilidad Biteral en bases de código PHP.

[!ref SDK de Biteral en Github](https://github.com/biteral-net/biteral-sdk-php)

### Instala el SDK con composer

```bash
composer require biteral/biteral-sdk-php
```

Con esto ya puedes empezar a integrar Biteral. Primero, crea un cliente:

```php
use Biteral\Client;
$client = new Client('ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ');
```

y realiza peticiones como [!badge getStatus]

```php
$status = $client->getStatus();
```

que devuelve un array con información sobre la conexión o el estado de la API:

```json
{
    "entity": "Status",
    "availableApiVersions": [
        {
            "entity": "ApiVersion",
            "version": "1.0.0",
            "status": "stable",
            "isDeprecated": false
        }
    ],
    "latestStableMajorApiVersion": 1,
    "requestMajorApiVersion": 1,
    "clientId": "cli_EeLdmCtWoWqNYj",
    "projectId": "prj_fHsHWBCvdnICot",
    "roles": [
        "ROLE_API_USER"
    ],
    "permissions": [
        "status"
    ],
    "serverTime": "2025-06-09T09:30:01+00:00",
    "environment": "prod"
}
```

### Uso

Las clases y métodos del SDK son un reflejo de la API, y hemos incluido ejemplos de uso del SDK en [las guías](/guide/integration-data/products) y en cada [endpoint](/api/endpoints/status).

!!!
Las sugerencias de código de tu IDE te mostrarán documentación sobre cada método y cómo utilizarlo.
!!!
