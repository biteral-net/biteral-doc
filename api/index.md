---
expanded: false
label: API
icon: /static/icons/technology/api.svg
order: 100
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

Los endpoints que aceptan datos reciben los datos en formato JSON. Por ejemplo, éste es el cuerpo de una petición [!badge variant="secondary" text="GET"] al endpoint [!badge /products](/api/endpoints/products/get) para obtener los datos de un producto:

```json
{
    "id": "pro_f28Jfk0i28iXIs"
}
```

De igual modo, las respuestas se dan también en formato JSON, por ejemplo:

```json
{
    "object": "product",
    "id": "pro_f28Jfk0i28iXIs",
    "data": {
        "code": "N39291",
        "isActive": true,
        "title": "Zapatillas deportivas urbanas para hombre – modelo AirFlow",
        "description": "Estas zapatillas combinan estilo y comodidad para el uso diario. Diseñadas con materiales transpirables, suela de goma antideslizante y plantilla ergonómica, son ideales tanto para caminar por la ciudad como para entrenar en interiores. El modelo AirFlow ofrece un ajuste perfecto y un diseño moderno que se adapta a cualquier look casual. Disponibles en varias tallas y colores.",
        "price": 49.95,
        "currency": "EUR",
        "attributes": [
            {"object": "product_attribute", "id": "att_3EoZrPlPxgvwj4", "name": "Material", "value": "Cuero"},
            {"object": "product_attribute", "id": "att_B7AIkhAqOUclJI", "name": "Color", "value": "negro con detalles en gris"},
            {"object": "product_attribute", "id": "att_MCa0JyCrr13OAU", "name": "Tallas disponibles", "value": "39, 40, 41, 42, 43, 44"},
            {"object": "product_attribute", "id": "att_n8BtH1ukAGxaFE", "name": "Suela", "value": "goma antideslizante"},
            {"object": "product_attribute", "id": "att_Sf9xT97JwARbOi", "name": "Peso", "value": "850g (par, talla 42)"},
            {"object": "product_attribute", "id": "att_vm470WEdaNrQNZ", "name": "Uso recomendado", "value": "Uso diario y entrenamiento ligero"},
        ],
        "brand": {
            "object": "brand",
            "id": "bra_fja9AiaijfaKf",
            "code": "OW142398",
            "name": "Nike"
        },
        "category": {
            "object": "product-category",
            "id": "cat_19FAkfaqcmz0f",
            "code": "MC418298",
            "title": "Zapatillas deportivas"
        }
    },
    "processingStatus": "ready",
    "createdAt": "2025-06-20T15:29:51+00:00",
    "updatedAt": "2025-06-21T12:33:02+00:00",
    "readyAt": "2025-06-21T12:33:08+00:00"
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
