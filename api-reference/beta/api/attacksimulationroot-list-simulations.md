---
title: "List simulations"
description: "List attack simulations of a tenant."
author: "Gopal-MSFT"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# List simulations
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

List attack simulations of a tenant.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | SecurityEvents.Read.All                     |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | SecurityEvents.Read.All                     |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/attackSimulation/simulations
```

## Optional query parameters
This method supports the following OData query parameters to help customize the response: `$count`, `$filter`, `$orderby`, `$skiptoken`, `$top`.

The following properties support `$filter` and `$orderby`: **attackTechnique**, **attackType**, **completionDateTime**, **displayName**, **isAutomated**, **launchDateTime**, **mode**, **status**.

Use `@odata.nextLink` for pagination.

The following are examples of their use:

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/attackSimulation/simulations?$count=true
GET /security/attackSimulation/simulations?$filter={property} eq '{property-value}'
GET /security/attackSimulation/simulations?$filter={property} eq '{property-value}'&$top=5
GET /security/attackSimulation/simulations?$orderby={property}
GET /security/attackSimulation/simulations?$top=1
```

For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [simulation](../resources/simulation.md) objects in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "list_simulation"
}
-->
``` http
GET https://graph.microsoft.com/beta/security/attackSimulation/simulations
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.simulation)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "id": "f1b13829-3829-f1b1-2938-b1f12938b1f1",
      "displayName": "Sample Simulation",
      "description": "Sample Simulation Description",
      "attackType": "social",
      "attackTechnique": "credentialHarvesting",
      "status": "scheduled",
      "createdDateTime": "2021-01-01T01:01:01.01Z",
      "createdBy": {
        "id": "99af58b9-ef1a-412b-a581-cb42fe8c8e21",
        "displayName": "Sample User",
        "email": "sampleuser@contoso.com"
      },
      "lastModifiedDateTime": "2021-01-01T01:01:01.01Z",
      "lastModifiedBy": {
        "id": "99af58b9-ef1a-412b-a581-cb42fe8c8e21",
        "displayName": "Sample User",
        "email": "sampleuser@contoso.com"
      },
      "launchDateTime": "2021-01-01T02:01:01.01Z",
      "completionDateTime": "2021-01-07T01:01:01.01Z",
      "includeAllAccountTargets": false,
      "enableRegionTimezoneDelivery": false,
      "mode": "real",
      "isAutomated": false,
      "cleanupArtifacts": false,
      "payloadSource": "global",
      "payloadDeliveryPlatform": "email",
      "trainingAssignmentPreference": "manual",
      "trainingContentPreference": "microsoft",
      "trainingDueDateTime": "2021-01-31T01:01:01.01Z"
    }
  ]
}
```
