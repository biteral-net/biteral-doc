---
label: Post
order: 100
icon: arrow-right
---
# /customers [!badge variant="success" text="POST"] [!badge variant="success" text="v1"]

Crear o modificar un cliente.

+++ :icon-project-roadmap: JSON request body

```json
{
    "code": "D314K1432",
    "country": "ES",
    "state": "Barcelona",
    "city": "Q11355",
    "yearBorn": 1990,
    "gender": 2,
    "metadata": {
        "currentDiscountRate": "10%",
        "isNew": true
    }
}
```

+++ :icon-book: Documentación

[!badge variant="danger" icon="lock" text="code"]
: Código de cliente, por ejemplo `D314K1432` [!badge variant="light" icon="arrow-both" text="255"]

[!badge variant="warning" text="isActive"]
: Indica si el cliente está habilitado para ser utilizado por los servicios de Biteral, como recomendaciones, búsqueda o análisis. Si no se incluye este campo al enviar o actualizar el cliente, se asume automáticamente que el cliente está activo `true`. Poner isActive a `false` permite mantener el cliente en el sistema sin que participe en ningún procesamiento o resultado de los servicios.

[!badge variant="warning" text="country"]
: País donde el cliente se ubica. Puede ser el nombre del país en inglés o en lengua nativa (por ejemplo, `España`), un código [ISO 3166-1 alpha-3](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3) (por ejemplo, `ESP`), un código [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) (por ejemplo, `ES`), un código [ISO 3166-1 numeric](https://en.wikipedia.org/wiki/ISO_3166-1_numeric) (por ejemplo, `724`) o un [WikiData ID](https://www.wikidata.org/wiki/Wikidata:Identifiers) (por ejemplo, `Q29`)

[!badge variant="warning" text="state"]
: Estado, región, comunidad o provincia donde el cliente se ubica. Puede ser el nombre del estado, región, comunidad o provincia en inglés o en lengua nativa (por ejemplo, `Barcelona`), un código [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) (por ejemplo, `ES-B`), un código [FIPS 10-4](https://en.wikipedia.org/wiki/FIPS_10-4) (por ejemplo, `36`) o un [WikiData ID](https://www.wikidata.org/wiki/Wikidata:Identifiers) (por ejemplo, `Q1492`)

[!badge variant="warning" text="city"]
: Ciudad o localidad donde el cliente se ubica. Puede ser el nombre de la ciudad o localidad en inglés o en lengua nativa (por ejemplo, `Antwerp`) o un [WikiData ID](https://www.wikidata.org/wiki/Wikidata:Identifiers) (por ejemplo, `Q11355`)

[!badge variant="warning" text="yearBorn"]
: Año de nacimiento del cliente, por ejemplo: `1990`

[!badge variant="warning" text="gender"]
: El género del cliente, de entre los posibles valores: `0` para género desconocido, `1` para masculino, `2` para femenino o `3` para otros géneros

[!badge variant="warning" text="metadata"]
: Datos adicionales que te resulten útiles cuando recibas el cliente como resultado de las herramientas de Biteral. Un objeto JSON [!badge variant="light" icon="arrow-both" text="60000"]. Por ejemplo:
```json
    {
        "currentDiscountRate": "10%",
        "isNew": true
    }
```

+++

### Actualizar un cliente

Para actualizar los datos sobre un cliente, realiza la misma petición `POST` a este endpoint con los nuevos datos.

Los datos que no especifiques mantendrán su valor anterior. Para eliminar un dato, pásalo como `null`

### Cargar varios clientes a la vez

Puedes cargar los clientes uno a uno, pero es más rápido cargarlos en bloques. Para hacerlo, pasa los clientes en forma de un array, por ejemplo:

```json
[
    {
        "code": "D314K1432",
        "country": "ES",
        "state": "Barcelona",
        "city": "Q11355",
        "yearBorn": 1990,
        "gender": 2,
        "metadata": {
            "currentDiscountRate": "10%",
            "isNew": true
        }
    }
    {
        "code" : "N4213S4123"
        ...
    },
    ...
]
```

!!!
Puedes cargar hasta 100 clientes a la vez utilizando este método
!!!

!!!
Cuando cargas muchos clientes a Biteral muy rápidamente, puede pasar un rato hasta que todos están disponibles para las herramientas de Biteral.
!!!
