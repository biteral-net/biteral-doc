---
title: PHP SDK
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
$biteralClient = new Client('ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ');
```

y realiza peticiones como [!badge getInfo]

```php
$status = $biteralClient->getInfo();
```

que devuelve un array con información sobre la conexión o el estado de la API:

```json
{
    "entity": "Status",
    "availableVersions": [
        "1"
    ],
    "requestVersion": "1",
    "latestVersion": "1",
    "apiKey": {
        "isValid": true,
        "isTesting": true,
        "created": "2025-03-11T12:03:38+00:00"
    },
    "connection": {
        "backendLatency": 83,
        "isThrottled": false
    },
    "status": {
        "state": "operational",
        "upcomingMaintenance": false
    },
    "features": {
        "productsIngest",
        "customersIngest",
        "eventsIngest",
        "personalizedRecommend",
        "naturalSearch",
        "trendAnalysis",
        "profileTags"
    }
}
```

### Utilizando el SDK

Las clases y métodos del SDK son un reflejo de la API, así que encontrarás la documentación sobre cómo utilizar el SDK en la [sección API](/api).

!!!
Si utilizas VSCode o similar, las sugerencias de código te mostrarán documentación sobre cada método y cómo utilizarlo.
!!!
