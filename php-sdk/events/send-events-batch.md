---
label: Enviar eventos en grupo
expanded: false
order: 995
icon: arrow-right
---
# Enviar eventos en grupo

Si vuestro sistema genera muchos eventos, es mejor enviar los eventos en grupo.

{{ include "/snippets/note_lots_of_events.md" }}

Para enviar eventos en grupo, en lugar de utilizar [!badge variant="light" text="events()->ingest()"] cada vez que se produce un evento en vuestro sistema, utiliza algún mecanismo que recopile periódicamente los eventos en diferido y utiliza [!badge variant="light" text="eventsBatchIngest()->ingest()"]. Mira cómo funciona:

```php
// Obtén un objeto EventsBatchIngestService para poder reutilizarlo
$eventsBatchIngestService = $client->eventsBatchIngest();

// Inicia una sesión de ingestión de events
$eventsBatchIngestService->startIngestionSession();

// Recorre tus eventos pendientes por enviar en un bucle
while ($event = $query->getRow()) {

    /**
     * Crea un objeto del tipo Payload que corresponda al evento que vas a enviar tal como hacías al
     * cargar eventos individualmente
     */
    switch ($event->getType()) {

        case 'sale':
            $eventPayload =
                new EventSalePayload([
                    'timestamp' => new DateTime('@'.$event->getTimestamp()),
                    'customerCode' => $event->getCustomerCode(),
                    'productCode' => $event->getProductCode()
                ]);
            break;

    }

    // Envía el evento para que sea cargado por bloques
    $eventsBatchIngestService->ingest($eventPayload);
}

// Cuando el bucle haya terminado, no olvides cerrar la sesión de ingestión
$batchIngestResult = $eventsBatchIngestService->finishIngestionSession();
```

> Cuando envías los eventos en grupo, sí es imprescindible especificar `timestamp`, puesto que el momento en que envias el evento puede ser diferente al momento en que realmente se produjo.

[!ref icon="arrow-right" text="Payloads de eventos disponibles"](/php-sdk/payloads/events)

### Ideas para recopilar los eventos en grupo

Una forma sencilla de enviar los eventos en grupo es crear un proceso que se ejecute regularmente cada `N` minutos, y que envíe todos los eventos que se hayan producido en los últimos `N` minutos en grupo, utilizando el método descrito arriba.

Algunas implementaciones más avanzadas guardan los eventos en una cola antes de enviarlos a Biteral, y realizan un envío en grupo de los eventos acumulados cuando la cola alcanza cierto tamaño. Esta cola de eventos puede implementarse de muchas formas, como una base de datos convencional tipo MySQL, un sistema en memoria como Redis o un bróker de mensajes como RabbitMQ.
