---
label: Introducción
order: 1000
icon: bookmark
expanded: true
---
# Integrar datos

Biteral analiza los datos de vuestros productos y el comportamiento de vuestros clientes para ofrecer herramientas como recomendaciones personalizadas, búsqueda en lenguaje natural, análisis de tendencias o etiquetas de cliente. Por eso, enviar datos precisos y actualizados a Biteral es clave para obtener el máximo rendimiento de la plataforma.

Aunque podéis enviarnos los datos en un archivo Excel o CSV, lo más recomendable es hacerlo a través de la API. Esto garantiza la máxima flexibilidad y permite que Biteral funcione en tiempo real, adaptándose siempre a los datos más recientes.

!!!secondary
En muchos casos, esta inmediatez es clave: por ejemplo, Biteral puede sugerir productos más adecuados justo después de una compra, aprovechando al máximo el momento de mayor interés del cliente.
!!!

Éstos son los tres tipos de datos clave que debes enviar a Biteral:

||| **![](/static/icons/product.svg){width="18"} Productos**
Los artículos que ofrecéis: nombre, descripción, precio, características, etc.
||| **![](/static/icons/customer.svg){width="18"} Clientes**
Identificadores internos para el seguimiento de cada cliente: ubicación, tipo de cliente, etc.
||| **![](/static/icons/event.svg){width="18"} Eventos**
Acciones que los clientes realizan: visitas a productos, compras, añadir al carrito, etc.
|||

### Decide el método de integración de datos

Para empezar, decide si vas a realizar peticiones a la API de Biteral directamente, o si prefieres utilizar el SDK para PHP de Biteral:

[!ref Cómo utilizar la API directamente](/api/intro)
[!ref Cómo utilizar el SDK para PHP](/php-sdk/intro)

!!!secondary
Si utilizas PHP te recomendamos que utilices el SDK, que permite conectar con Biteral muy fácilmente y proporciona herramientas adicionales que te facilitarán enormemente la integración.
!!!
