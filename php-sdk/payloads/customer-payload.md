---
label: CustomerPayload
expanded: false
icon: arrow-right
order: 970
---
# CustomerPayload

Representa uno de vuestros clientes, con únicamente los datos que proporcionaste al añadirlo a Biteral.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="isActive"]|bool|Indica si este cliente está activo en las herramientas de Biteral.
[!badge icon="screen-full" text="code"]|string|Código del cliente. Puede ser cualquier identificador único que utilicéis internamente o públicamente para identificar vuestro cliente. Puede utilizarse un código arbitrario de cualquier tipo, incluyendo números, letras u otros caracteres. El único requisito es que debe corresponder específicamente sólo a uno de vuestros clientes. Por ejemplo: `D314K1432`
[!badge icon="screen-full" text="country"]|string|País donde el cliente se ubica, un código [ISO 3166-1 alpha-3](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3) (por ejemplo, `ESP`). Cuando se envían datos, también acepta el nombre del país en inglés o en lengua nativa (por ejemplo, `España`), códigos [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) (por ejemplo, `ES`), [ISO 3166-1 numeric](https://en.wikipedia.org/wiki/ISO_3166-1_numeric) (por ejemplo, `724`) y [WikiData ID](https://www.wikidata.org/wiki/Wikidata:Identifiers) (por ejemplo, `Q29`)
[!badge icon="screen-full" text="state"]|string|Estado, región, comunidad o provincia donde el cliente se ubica, un código [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) (por ejemplo, `ES-B`). Cuando se envían datos, también acepta el nombre del estado, región, comunidad o provincia en inglés o en lengua nativa (por ejemplo, `Barcelona`), códigos [FIPS 10-4](https://en.wikipedia.org/wiki/FIPS_10-4) (por ejemplo, `36`) y [WikiData ID](https://www.wikidata.org/wiki/Wikidata:Identifiers) (por ejemplo, `Q1492`)
[!badge icon="screen-full" text="city"]|string|Ciudad o localidad donde el cliente se ubica, un [WikiData ID](https://www.wikidata.org/wiki/Wikidata:Identifiers) (por ejemplo, `Q11355`). Cuando se envían datos, también acepta el nombre de la ciudad en inglés o en lengua nativa (por ejemplo, `Antwerp`)
[!badge icon="screen-full" text="yearBorn"]|int|Año de nacimiento del cliente. Por ejemplo: `1990`
[!badge icon="screen-full" text="gender"]|int|El género del cliente, de entre los posibles valores: `0` para género desconocido, `1` para masculino, `2` para femenino o `3` para otros géneros
[!badge icon="screen-full" text="metadata"]|string|Datos adicionales que te resulten útiles cuando recibas el cliente como resultado de las herramientas de Biteral en forma de una cadena JSON.
