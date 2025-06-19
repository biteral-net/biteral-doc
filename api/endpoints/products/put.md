---
label: Put
order: 90
---
# /products
[!badge variant="success" text="PUT"] [!badge variant="success" text="v1"]

Reemplaza todo el contenido del producto en lugar de cambiar sólo algunos datos como haría una petición [!badge variant="secondary" text="PATCH"]. Esto significa que si omites algún dato (por ejemplo, la descripción o los atributos), esos datos se eliminarán del producto en Biteral.

+++ Resultado
```json
{
    "entity": "Status",
    "availableApiVersions": [
        {
            "entity": "ApiVersion",
            "version": "1.0.0",
            "status": "stable",
            "isDeprecated": false
        }
    ],
    "latestStableMajorApiVersion": 1,
    "requestMajorApiVersion": 1,
    "clientId": "cli_EeLdmCtWoWqNYj",
    "projectId": "prj_fHsHWBCvdnICot",
    "roles": [
        "ROLE_API_USER"
    ],
    "permissions": [
        "status"
    ],
    "serverTime": "2025-06-09T09:30:01+00:00",
    "environment": "prod"
}
```
+++
