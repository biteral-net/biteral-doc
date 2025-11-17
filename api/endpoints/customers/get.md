---
label: Get
order: 70
icon: arrow-right
---
# /customers [!badge variant="success" text="GET"] [!badge variant="success" text="v1"]

Obtener un cliente.

+++ :icon-tasklist: Parámetros

Especifica uno de estos dos parámetros para obtener un cliente a través de su código o de su Id en Biteral:

[!badge variant="warning" text="code"]
: Código de cliente, por ejemplo `D314K1432`

[!badge variant="warning" text="id"]
: Identificador del cliente en Biteral, por ejemplo: `cus_C0fCLwecMysLj9`

+++ :icon-project-roadmap: Resultado

```json
{
    "object": "customer",
    "id": "cus_C0fCLwecMysLj9",
    "createdAt": "2025-11-14T18:27:46+00:00",
    "updatedAt": "2025-11-15T09:16:03+00:00",
    "projectId": "prj_18vn8R74uvSijf",
    "payload": {
        "code": "D314K1432",
        "isActive": true,
        "country": "ESP",
        "state": "ES-B",
        "city": "Q11355",
        "yearBorn": 1990,
        "gender": 2,
        "metadata": {
            "currentDiscountRate": "10%",
            "isNew": true
        }
    }
}
```
+++
