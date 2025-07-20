---
label: Instalación
icon: arrow-right
order: 1000
---
# Instalar el SDK para PHP

El SDK de Biteral PHP es un package para composer que te permite integrar con facilidad Biteral en proyectos PHP versión 5.6 y superiores.

[!ref SDK de Biteral en GitHub](https://github.com/biteral-net/biteral-sdk-php)

Añade el SDK a tu proyecto:

```bash
composer require biteral/biteral-sdk-php
```

Crea un cliente utilizando tu API key:

```php
use Biteral\Client;
$client = new Client('ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ');
```

y ya puedes realizar peticiones, como por ejemplo:

```php
$status = $client->status()->get();
```

[!badge status()->get()] devuelve una entidad [!badge variant="info" text="Status"](/php-sdk/entities/status) con la que puedes obtener información sobre la conexión o el estado de la API, y es una forma sencilla de comprobar que la conexión con Biteral funciona correctamente. Por ejemplo:

```php
if ($status->latestStableMajorApiVersion === $status->requestMajorApiVersion) {
    echo "Estás utilizando la versión de API más reciente";
}
```
