---
label: Enviar eventos
expanded: false
order: 1000
icon: arrow-right
---
# Enviar eventos

Cada vez que uno de vuestros clientes realice una de las acciones contempladas por Biteral, como comprar un producto o ver una categoría, debes envíar un evento a Biteral para alimentar las herramientas de inteligencia artificial.

!!!
Hay varios [tipos de eventos](/php-sdk/payloads/events) que debes enviar a Biteral. No es necesario implementarlos todos en vuestro sistema, pero sí es recomendable para que Biteral pueda ofrecer un análisis más completo y preciso del comportamiento del cliente.
!!!

### Enviar un evento

Llama a [!badge variant="info" text="events()->ingest"](/php-sdk/events/send-events) con uno de los [payloads de eventos](/php-sdk/payloads/events) disponibles que corresponda al evento que deseas enviar, por ejemplo: [!badge variant="info" text="EventSalePayload"](/php-sdk/payloads/events/event-sale-payload) como parámetro:

```php
use Biteral\Payload\Event\EventSalePayload;

$eventPayload =
    new EventSalePayload([
        'timestamp' => new DateTime('2025-11-15 15:53:15'),
        'customerCode' => 'D314K1432',
        'productCode' => 'N30122'
    ]);

$client->events()->ingest($eventPayload);
```

> Si envías los eventos en el mismo momento en que se producen, no es necesario especificar `timestamp`.

[!ref icon="arrow-right" text="Payloads de eventos disponibles"](/php-sdk/payloads/events)


### Cuándo enviar un evento

Lo más sencillo es enviar los eventos en el mismo instante en que se producen en tu sistema. Además, esto hará que los resultados de Biteral estén actualizados casi en tiempo real. Sin embargo, si vuestro sistema genera muchos eventos, es mejor enviar los eventos en grupo. Continúa a la siguiente sección para aprender cómo hacerlo.