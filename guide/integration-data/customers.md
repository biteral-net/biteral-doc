---
label: Clientes
order: 980
icon: /static/icons/customer.svg
---
# ![](/static/icons/customer.svg){width="40"} Integrar clientes

Biteral utiliza información sobre vuestros clientes para para alimentar herramientas como las recomendaciones personalizadas. Los datos de vuestros clientes siempre se envían anonimizados, de forma que no existe un vínculo directo entre la información que envías y el cliente final.

### Cargar un cliente

==- :icon-file-code: **Con PHP**

Llama a [!badge variant="info" text="customers()->ingest"](/php-sdk/customers/add-customers) con un objeto [!badge variant="info" text="CustomerPayload"](/php-sdk/payloads/customer-payload) como parámetro.

[!ref icon="arrow-right" text="Cargar un cliente con PHP"](/php-sdk/customers/add-customers)

==- **![](/static/icons/technology/api.svg){width="18"} Con la API**

Haz una petición [!badge variant="success" text="POST"] al endpoint [!badge /customers](/api/endpoints/customers/post)

[!ref icon="arrow-right" text="Cargar un cliente con la API"](/api/endpoints/customers/post)

==-

### Cargar muchos clientes a la vez

Igual que cuando cargas muchos productos a la vez, puedes cargar varios clientes de forma eficiente utilizando el método de carga masiva de clientes:

[!ref icon="arrow-right" text="Carga masiva con PHP"](/php-sdk/customers/add-customers-batch)
[!ref icon="arrow-right" text="Carga masiva con la API"](/api/endpoints/customers/post/#cargar-varios-clientes-a-la-vez)

### Otras operaciones con clientes

También puedes realizar otras operaciones con clientes, como modificarlos, desactivarlos o eliminarlos:

[!ref icon="arrow-right" text="Otras operaciones con clientes con PHP"](/php-sdk/customers/update-customers)
[!ref icon="arrow-right" text="Otras operaciones con clientes con la API"](/api/endpoints/customers/post)
