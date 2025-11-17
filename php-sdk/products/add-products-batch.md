---
label: Carga masiva
expanded: false
order: 995
icon: arrow-right
---
# Carga masiva de productos

Si necesitas cargar muchos productos en Biteral, llamar a [!badge variant="light" text="products()->ingest()"] por cada producto que quieres cargar es lento, y puede provocar errores por consumo excesivo de memoria.

En su lugar, usa [!badge variant="light" text="productsBatchIngest()->ingest()"], que está diseñado específicamente para cargas masivas. Este método agrupa los productos de forma óptima para maximizar la velocidad y reducir el riesgo de problemas relacionados con el uso de recursos. Mira cómo funciona:

```php
// Obtén un objeto ProductsBatchIngestService para poder reutilizarlo
$productsBatchIngestService = $client->productsBatchIngest();

// Inicia una sesión de ingestión de productos
$productsBatchIngestService->startIngestionSession();

// Recorre los productos en un bucle tal como lo harías normalmente con tu base de datos
while ($product = $query->getRow()) {

    // Crea un objeto ProductPayload tal como hacías al cargar productos individualmente
    $productPayload =
        new ProductPayload([
            'code' => $product->getCode(),
            'title' => $product->getTitle(),
            [...]
        ]);

    // Envía el producto para que sea cargado por bloques
    $productsBatchIngestService->ingest($productPayload);
}

// Cuando el bucle haya terminado, no olvides cerrar la sesión de ingestión
$batchIngestResult = $productsBatchIngestService->finishIngestionSession();
```

!!!
Cuando cargas muchos productos a Biteral muy rápidamente, puede pasar un rato hasta que todos están disponibles para las herramientas de Biteral.
!!!
