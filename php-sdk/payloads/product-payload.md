---
label: ProductPayload
expanded: false
icon: arrow-right
---
# ProductPayload

Representa uno de vuestros productos, con únicamente los datos que proporcionaste al añadirlo a Biteral.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="code"]|string|Código del producto. Puede ser cualquier identificador único que utilicéis internamente o públicamente para identificar vuestro producto. Puede utilizarse un SKU, un código EAN, o un código arbitrario de cualquier tipo, incluyendo números, letras u otros caracteres. El único requisito es que debe corresponder específicamente sólo a un producto de vuestro catálogo. por ejemplo: `N841812`
[!badge icon="screen-full" text="title"]|string|Título del producto
[!badge icon="screen-full" text="description"]|string|Descripción del producto
[!badge icon="screen-full" text="attributes"]|array< [!badge variant="info" text="AttributePayload"](/php-sdk/payloads/attribute-payload) >|Atributos del producto
[!badge icon="screen-full" text="brand"]|[!badge variant="info" text="BrandPayload"](/php-sdk/payloads/brand-payload)|Marca del producto
[!badge icon="screen-full" text="category"]|[!badge variant="info" text="CategoryPayload"](/php-sdk/payloads/category-payload)|Categoría del producto
[!badge icon="screen-full" text="price"]|[!badge variant="info" text="PricePayload"](/php-sdk/payloads/price-payload)|Precio del producto
