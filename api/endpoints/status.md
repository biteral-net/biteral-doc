---
label: /status
icon: arrow-right
order: 1000
---
# /status [!badge variant="success" text="GET"] [!badge variant="success" text="v1"]

Obtiene información sobre el estado de la API y otros parámetros útiles como tus credenciales, la versión que estás utilizando y las versiones disponibles.

+++ Resultado
```json
{
    "object": "status",
    "data": {
        "availableApiVersions": [
            {
                "object": "api_version",
                "data": {
                    "version": "1.0.0b",
                    "status": "beta",
                    "isDeprecated": false
                }
            }
        ],
        "latestStableMajorApiVersion": 1,
        "requestMajorApiVersion": 1,
        "clientId": "cli_FnPwntyztB5vXi",
        "projectId": "prj_DXwRnr27kHGcCZ",
        "roles": [
            "ROLE_API_USER"
        ],
        "permissions": [
            "status",
            "depotIngest",
            "depotFetch",
            "depotDelete"
        ],
        "serverTime": "2025-07-09T11:00:32+00:00",
        "environment": "prod"
    }
}
```
+++
