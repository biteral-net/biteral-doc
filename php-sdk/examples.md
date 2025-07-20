---
label: Ejemplos
icon: arrow-right
order: 100
---
El SDK incluye varios ejemplos en [/examples](https://github.com/biteral-net/biteral-sdk-php/tree/main/examples) que puedes utilizar como referencia.

!!!
Si instalaste el SDK con composer, encontrarás todos los ejemplos en el directorio `vendor/biteral-net/biteral-sdk-php/examples` de tu proyecto.
!!!

Puedes ejecutar los ejemplos utilizando el script `bin/example` incluído en el SDK:

Primero asegúrate de que `bin/example` es ejecutable:

```bash
chmod +x bin/example
```

Ejecuta `bin/example` sin ningún parámetro para obtener una lista de los ejemplos disponibles:

```bash
Usage: bin/example <example-name>

Available examples:

  product-delete - Remove one product from a Biteral project
  product-get - Get one product from a Biteral project
  product-ingest-massive - Ingest many products into a Biteral project
  product-ingest - Ingest one product into a Biteral project
  simple-request - A simple request to first learn how the SDK works
  status - Get Biteral's API status and info about your request
  [...]
```
