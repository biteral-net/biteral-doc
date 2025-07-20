---
expanded: false
label: PHP SDK
icon: file-code
order: 200
---
# PHP SDK

El SDK de Biteral PHP es un package para composer que te permite integrar con facilidad Biteral en bases de código PHP.

[!ref SDK de Biteral en GitHub](https://github.com/biteral-net/biteral-sdk-php)

### Instala el SDK con composer

```bash
composer require biteral/biteral-sdk-php
```

Con esto ya puedes empezar a integrar Biteral. Primero, crea un cliente:

```php
use Biteral\Client;
$client = new Client('ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ');
```

y realiza peticiones como [!badge status()->get()]

```php
$status = $client->status()->get();
```

que devuelve una entidad [!badge variant="info" text="Status"](/php-sdk/entities/status) con el que puedes obtener información sobre la conexión o el estado de la API, por ejemplo:

```php
if ($status->latestStableMajorApiVersion === $status->requestMajorApiVersion) {
    echo "Estás utilizando la versión de API más reciente";
}
```
