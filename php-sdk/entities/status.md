---
label: Status
expanded: false
icon: arrow-right
order: 1100
---
# Status

Representa el estado actual de la API de Biteral, y además proporciona información sobre tu petición, tus credenciales y otros datos útiles como las versiones de API disponibles, o la versión que estás actualizando actualmente.

### Propiedades

||
---|---|---
[!badge icon="screen-full" text="availableApiVersions"]|array\<[!badge variant="info" text="ApiVersion"](/php-sdk/payloads/api-version-payload)\>|Las versiones de la API que están disponibles.
[!badge icon="screen-full" text="latestStableMajorApiVersion"]|int|La versión mayor de API que se considera estable actualmente. Por ejemplo: `1`.
[!badge icon="screen-full" text="requestMajorApiVersion"]|int|La versión mayor de API que se ha utilizado para esta petición a la API. Por ejemplo: `1`.
[!badge icon="screen-full" text="clientId"]|string|El ID de cliente con el que se está realizando esta petición a la API. Por ejemplo: `cli_2YyNEfr5gcl139`.
[!badge icon="screen-full" text="projectId"]|string|El ID de proyecto con el que se está realizando esta petición a la API. Por ejemplo: `prj_skd2kjn1j4aO1K`.
[!badge icon="screen-full" text="roles"]|array\<string\>|Los roles que posee la API key utilizada en esta petición a la API. Por ejemplo: `["ROLE_API_USER"]`.
[!badge icon="screen-full" text="permissions"]|array\<string\>|Los permisos que posee la API key utilizada en esta petición a la API. Por ejemplo: `["all"]`.
[!badge icon="screen-full" text="serverTime"]|DateTimeImmutable|La fecha y hora del servidor de API en el momento de realizar la petición. Por ejemplo: ` 2025-11-26T09:36:57+00:00`.
[!badge icon="screen-full" text="environment"]|string|El entorno en el que está funcionando la API. Por ejemplo `prod`