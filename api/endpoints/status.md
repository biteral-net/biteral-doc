---
label: /status
icon: arrow-right
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
        "clientId": "cli_mKXzG4ZP8UwXYu",
        "projectId": "prj_KCNAunhFSSS6yK",
        "roles": [
            "ROLE_API_USER"
        ],
        "permissions": [
            "status",
            "ingest"
        ],
        "serverTime": "2025-07-02T17:52:44+00:00",
        "environment": "prod"
    }
}
```
+++
