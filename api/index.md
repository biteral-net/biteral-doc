---
title: API
---
# API

La API REST de Biteral es el principal método de conexión de vuestro sistema a Biteral, y es el método recomendado para integraciones de cualquier tamaño flexibles y fiables.

Si utilizas PHP, es recomendable utilizar el [SDK de Biteral para PHP](/php-sdk).

### Antes de empezar

1. Crea una cuenta en [Biteral](https://biteral.net/signup)
1. Obtén vuestra API key de pruebas desde el [dashboard](https://biteral.net/dashboard)

==- Limitaciones de la API key de pruebas
La API key de pruebas os permite utilizar Biteral gratuitamente, ideal para realizar pruebas desde vuestro entorno de desarrollo y ver resultados reales sobre cómo funcionaría Biteral con vuestro sistema.

Sin embargo, la API key de pruebas tiene algunos límites:

{.list-icon}
- :icon-alert: Algunos endpoints tienen el máximo de peticiones por segundo limitado.
- :icon-alert: Algunos endpoints sólo pueden recibir cierto número de peticiones por día.
===

### Cómo conectar

Realiza peticiones [!badge variant="light" text="HTTPS"] a [!badge variant="light" text="https:\/\/api.biteral.net/v1"] incluyendo vuestra API key en el header [!badge variant="light" text="X-Key"]:

+++ Curl
```shell
curl \
    -G https://api.biteral.net/v1/info \
    -H 'X-Key: ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ'
```
+++ PHP
```php
use Biteral\Client;
$biteralClient = new Client('ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ');
$status = $biteralClient->getInfo();
print_r($status);
```
+++

### Códigos de respuesta

| Código | Tipo | Descripción |
|-----------------|------|-------------|
| 200 | OK | La solicitud se completó exitosamente. |
| 201 | Created | La solicitud se completó y se creó un nuevo recurso. |
| 400 | Bad Request | La petición se realizó de forma incorrecta, o alguno de los datos incluidos no tenía el formato o la sintaxis correcta. |
| 401 | Unauthorized | La solicitud requiere autenticación, y no proporcionaste una API Key válida. |
| 403 | Forbidden | El cliente no tiene permiso para acceder al recurso solicitado. |
| 404 | Not Found | El recurso solicitado no se encontró. |
| 405 | Method Not Allowed | El método HTTP utilizado no está permitido para el recurso solicitado. |
| 429 | Too Many Requests | Realizaste demasiadas solicitudes en un período de tiempo corto. |
| 500 | Internal Server Error | El servidor encontró un error interno que impidió procesar la solicitud. |
| 503 | Service Unavailable | El servidor no está disponible temporalmente debido a mantenimiento o sobrecarga. |
