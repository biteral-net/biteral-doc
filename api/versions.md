---
label: Versiones
order: 900
icon: arrow-right
---
# Versiones

Cada vez que añadimos o mejoramos funcionalidades que implican cambios en la especificación de la API y podrían afectar a tu implementación, publicamos una nueva versión principal. La versión anterior sigue disponible, por lo que puedes estar seguro de que tu integración seguirá funcionando sin interrupciones, incluso si actualizamos la API en el futuro.

Por eso, es imprescindible que añadas el header [!badge variant="warning" text="X-API-Version"] a las peticiones a la API, que especifica la versión de la API que quieres utilizar.

> En la documentación marcamos cada funcionalidad con una etiqueta como [!badge variant="success" text="v1"] para que sepas en qué versión está disponible.

> Para obtener información sobre las versiones disponibles, utiliza el endpoint [!badge variant="dark" text="/status"](/api/endpoints/status.md)
