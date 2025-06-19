---
label: /status
---
# /status
[!badge variant="success" text="GET"] [!badge variant="success" text="v1"]

Obtener información sobre el estado de la API y otros parámetros útiles como tus credenciales, la versión que estás utilizando y las versiones disponibles.

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
