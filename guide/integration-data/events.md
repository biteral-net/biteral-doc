---
label: Eventos
order: 970
icon: /static/icons/event.svg
---
# ![](/static/icons/event.svg){width="40"} Integrar eventos

Los eventos son las acciones que vuestros clientes realizan, y permiten a Biteral aprender cómo interactúan con vuestros productos. Por ejemplo, algunos de los eventos más importantes que Biteral recopila son la compra de productos, la navegación por vuestro catálogo o incluso las devoluciones.

### Enviar un evento

==- :icon-file-code: **Con PHP**

Llama a [!badge variant="info" text="events()->ingest"](/php-sdk/events/send-events) con uno de los [payloads de eventos](/php-sdk/payloads/events) disponibles que corresponda al evento que deseas enviar, por ejemplo: [!badge variant="info" text="EventSalePayload"](/php-sdk/payloads/events/event-sale-payload) como parámetro.

[!ref icon="arrow-right" text="Enviar un evento con PHP"](/php-sdk/events/send-events)

==- **![](/static/icons/technology/api.svg){width="18"} Con la API**

Haz una petición [!badge variant="success" text="POST"] al endpoint [!badge /events](/api/endpoints/events/post)

[!ref icon="arrow-right" text="Enviar un evento con la API"](/api/endpoints/events/post)

==-

### Cuándo enviar un evento

Lo más sencillo es enviar los eventos en el mismo instante en que se producen en tu sistema. Además, esto hará que los resultados de Biteral estén actualizados casi en tiempo real. Sin embargo, si vuestro sistema genera muchos eventos, es mejor enviar los eventos en grupo:

[!ref icon="arrow-right" text="Enviar eventos en grupo con PHP"](/php-sdk/events/send-events-batch)
[!ref icon="arrow-right" text="Enviar eventos en grupo con la API"](/api/endpoints/events/post/#enviar-varios-eventos-a-la-vez)

{{ include "/snippets/note_lots_of_events.md" }}
