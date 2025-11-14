---
label: ProductPayload
expanded: false
icon: arrow-right
order: 1000
---
# ProductPayload

Representa uno de vuestros productos, con únicamente los datos que proporcionaste al añadirlo a Biteral.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="isActive"]|bool|Indica si este producto está activo en las herramientas de Biteral.
[!badge icon="screen-full" text="code"]|string|Código del producto. Puede ser cualquier identificador único que utilicéis internamente o públicamente para identificar vuestro producto. Puede utilizarse un SKU, un código EAN, o un código arbitrario de cualquier tipo, incluyendo números, letras u otros caracteres. El único requisito es que debe corresponder específicamente sólo a un producto de vuestro catálogo. Por ejemplo: `N841812`
[!badge icon="screen-full" text="title"]|string|Título del producto
[!badge icon="screen-full" text="description"]|string|Descripción del producto
[!badge icon="screen-full" text="attributes"]|array< [!badge variant="info" text="ProductAttributePayload"](/php-sdk/payloads/product-attribute-payload) >|Atributos del producto
[!badge icon="screen-full" text="brand"]|[!badge variant="info" text="BrandPayload"](/php-sdk/payloads/brand-payload)|Marca del producto
[!badge icon="screen-full" text="category"]|[!badge variant="info" text="CategoryPayload"](/php-sdk/payloads/category-payload)|Categoría del producto
[!badge icon="screen-full" text="price"]|[!badge variant="info" text="PricePayload"](/php-sdk/payloads/price-payload)|Precio del producto
[!badge icon="screen-full" text="imageUrl"]|string|La URL de la imagen del producto, preferiblemente una imagen de aproximadamente 600 píxeles de ancho.
[!badge icon="screen-full" text="url"]|string|La URL pública del producto.
[!badge icon="screen-full" text="metadata"]|string|Datos adicionales que te resulten útiles cuando recibas el producto como resultado de las herramientas de Biteral en forma de una cadena JSON.
