---
label: Productos
order: 990
icon: /static/icons/product.svg
---
# ![](/static/icons/product.svg){width="40"} Integrar productos

Lo más recomendable es comenzar cargando todos los productos disponibles en vuestro e-commerce para que Biteral pueda empezar a trabajar con ellos, pero primero veamos cómo cargar un único producto:

### Cargar tu primer producto

==- :icon-file-code: **Con PHP**

Una vez hayas [instalado el SDK](/php-sdk/install), llama a [!badge variant="info" text="products()->ingest"](/php-sdk/products/add-products) con un objeto [!badge variant="info" text="ProductPayload"](/php-sdk/payloads/product-payload) como parámetro.

[!ref icon="arrow-right" text="Cargar un producto con PHP"](/php-sdk/products/add-products)

==- **![](/static/icons/technology/api.svg){.custom-icon}{width="18"} Con la API**

Una vez hayas aprendido [cómo conectar con la API](/api/connect), haz una petición [!badge variant="success" text="POST"] al endpoint [!badge /products](/api/endpoints/products/post)

[!ref icon="arrow-right" text="Cargar un producto con la API"](/api/endpoints/products/post)
==-

### Cargar muchos productos a la vez

Al cargar todo vuestro catálogo, realizar una petición por cada producto sería muy lento. En su lugar, utiliza el método de carga masiva de productos:

[!ref icon="arrow-right" text="Carga masiva con PHP"](/php-sdk/products/add-products-batch)
[!ref icon="arrow-right" text="Carga masiva con la API"](/api/endpoints/products/post/#cargar-varios-productos-a-la-vez)

### Otras operaciones con productos

También puedes realizar otras operaciones con productos, como modificarlos, desactivarlos o eliminarlos:

[!ref icon="arrow-right" text="Otras operaciones con productos con PHP"](/php-sdk/products/update-products)
[!ref icon="arrow-right" text="Otras operaciones con productos con la API"](/api/endpoints/products/post)