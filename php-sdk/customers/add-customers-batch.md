---
label: Carga masiva
expanded: false
order: 995
icon: arrow-right
---
# Carga masiva de clientes

Si necesitas cargar muchos clientes en Biteral, llamar a [!badge variant="light" text="customers()->ingest()"] por cada cliente que quieres cargar es lento, y puede provocar errores por consumo excesivo de memoria.

En su lugar, usa [!badge variant="light" text="customersBatchIngest()->ingest()"], que está diseñado específicamente para cargas masivas. Este método agrupa los clientes de forma óptima para maximizar la velocidad y reducir el riesgo de problemas relacionados con el uso de recursos. Mira cómo funciona:

```php
// Obtén un ClientsBatchIngestService para poder reutilizarlo
$clientsBatchIngestService = $client->clientsBatchIngest();

// Inicia una sesión de ingestión de clientes
$clientsBatchIngestService->startIngestionSession();

// Recorre los clientes en un bucle tal como lo harías normalmente con tu base de datos
while ($client = $query->getRow()) {

    // Crea un objeto ClientPayload tal como hacías al cargar clientes individualmente
    $clientPayload =
        new ClientPayload([
            'code' => $client->getCode(),
            'country' => $client->getCountry(),
            'state' => $client->getState(),
            'city' => $client->getCity(),
            'yearBorn' => $client->getYearBorn(),
            [...]
        ]);

    // Envía el cliente para que sea cargado por bloques
    $clientsBatchIngestService->ingest($clientPayload);
}

// Cuando el bucle haya terminado, no olvides cerrar la sesión de ingestión
$batchIngestResult = $clientsBatchIngestService->finishIngestionSession();
```
