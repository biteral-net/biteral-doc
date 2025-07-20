---
label: Conectar
icon: arrow-right
order: 1000
---
# Conectar con la API

La API REST de Biteral es el principal método de conexión de vuestro sistema a Biteral, y es el método recomendado para integraciones de cualquier tamaño flexibles y fiables.

Si utilizas PHP, es muy recomendable utilizar el [SDK de Biteral para PHP](/php-sdk/install), que proporciona un interfaz extremadamente sencillo y fiable para trabajar con la API de Biteral.

### Antes de empezar

1. Crea una cuenta en [Biteral](https://biteral.net/signup)
1. Obtén vuestra API key de pruebas desde el [dashboard](https://biteral.net/dashboard)

==- Limitaciones de la API key de pruebas
La API key de pruebas os permite utilizar Biteral gratuitamente, ideal para realizar pruebas desde vuestro entorno de desarrollo y ver resultados reales sobre cómo funcionaría Biteral con vuestro sistema. Sin embargo, la API key de pruebas tiene algunos límites:

!!!warning Límite de peticiones por segundo estricto
Algunos endpoints tienen el máximo de peticiones por segundo limitado, así que es posible que obtengas un código de respuesta `429 Too Many Requests` al utilizar una API key de pruebas y realizar demasiadas peticiones en un breve espacio de tiempo.
!!!

!!!warning Límite máximo de peticiones diarias
Algunos endpoints sólo pueden recibir cierto número de peticiones por día. Al utilizar una API key de pruebas, si alcanzas este límite obtendrás también un código de respuesta `429 Too Many Requests`
!!!

===

### Cómo conectar

Realiza peticiones [!badge variant="light" text="HTTPS"] a [!badge variant="light" text="https:\/\/api.biteral.net"] incluyendo los siguientes headers:

- [!badge variant="warning" text="X-API-Key"] Vuestra API key
- [!badge variant="warning" text="X-API-Version"] La versión principal de la API que vas a utilizar, por ejemplo: [!badge variant="light" text="1"]

+++ Curl
```shell
curl \
    -G https://api.biteral.net/status \
    -H 'X-API-Key: ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ' \
    -H 'X-API-Version: 1'
```
+++ PHP
```php
use Biteral\Client;
$client = new Client('ux3HzRTaLGKvZjTb7ufaFUgJPvXbcNX7DWbnWAAUxQjHYqZJ');
$status = $client->getInfo();
print_r($status);
```
+++

### Enviar y recibir datos en la API

Los endpoints [!badge variant="success" text="POST"], [!badge variant="success" text="PUT"] y [!badge variant="success" text="PATCH"] normalmente aceptan los datos en formato JSON a través del `body` de la petición. Por ejemplo, éste es el cuerpo de una petición [!badge variant="success" text="POST"] al endpoint [!badge /products](/api/endpoints/products/post) para enviar un producto a Biteral:

```json
{
    "code": "N30123",
    "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
    "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores."
}
```

Otros endpoints del tipo [!badge variant="success" text="GET"] o [!badge variant="success" text="DELETE"] aceptan datos a través de los parámetros en la URL de la petición. Por ejemplo, ésta es la URL para una petición [!badge variant="success" text="GET"] al endpoint [!badge /products](/api/endpoints/products/get) que obtiene los datos de un producto:

```
https://api.biteral.net/products?code=B00YUU43VS
```

Todos los endpoints responden siempre en formato JSON, por ejemplo:

```json
{
    "object": "product",
    "id": "pro_Fm3NC30gQHfxIP",
    "createdAt": "2025-07-09T10:21:11+00:00",
    "updatedAt": "2025-07-09T10:42:48+00:00",
    "isActive": true,
    "payload": {
        "code": "N30122",
        "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
        "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.",
        "attributes": null,
        "brand": null,
        "category": null,
        "price": {
            "amount": "49.95",
            "currency": "EUR"
        }
    }
}
```

### Códigos de respuesta

Los códigos HTTP de respuesta indican si la petición se realizó con éxito, o si se produjo algún error:

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
