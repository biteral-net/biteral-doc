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
// Obtén un objeto CustomersBatchIngestService para poder reutilizarlo
$customersBatchIngestService = $client->customersBatchIngest();

// Inicia una sesión de ingestión de clientes
$customersBatchIngestService->startIngestionSession();

// Recorre los clientes en un bucle tal como lo harías normalmente con tu base de datos
while ($customer = $query->getRow()) {

    // Crea un objeto CustomerPayload tal como hacías al cargar clientes individualmente
    $customerPayload =
        new CustomerPayload([
            'code' => $customer->getCode(),
            'country' => $customer->getCountry(),
            'state' => $customer->getState(),
            'city' => $customer->getCity(),
            'yearBorn' => $customer->getYearBorn(),
            [...]
        ]);

    // Envía el cliente para que sea cargado por bloques
    $customersBatchIngestService->ingest($customerPayload);
}

// Cuando el bucle haya terminado, no olvides cerrar la sesión de ingestión
$batchIngestResult = $customersBatchIngestService->finishIngestionSession();
```

!!!
Cuando cargas muchos clientes a Biteral muy rápidamente, puede pasar un rato hasta que todos están disponibles para las herramientas de Biteral.
!!!
