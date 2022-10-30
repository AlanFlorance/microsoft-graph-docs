---
title: "List updatePolicy"
description: "Get the updatePolicy resources from the updatePolicy navigation property."
author: "**TODO: Provide Github Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.prod: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: apiPageType
---

# List updatePolicy
Namespace: microsoft.graph.windowsUpdates

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the updatePolicy resources from the updatePolicy navigation property.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|**TODO: Provide applicable permissions.**|
|Delegated (personal Microsoft account)|**TODO: Provide applicable permissions.**|
|Application|**TODO: Provide applicable permissions.**|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /admin/windows/updates/updatePolicies/{updatePolicyId}/complianceChanges/{complianceChangeId}/updatePolicy
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [updatePolicy](../resources/updatepolicy.md) objects in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "list_updatepolicy"
}
-->
``` http
GET https://graph.microsoft.com/beta/admin/windows/updates/updatePolicies/{updatePolicyId}/complianceChanges/{complianceChangeId}/updatePolicy
```


### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.windowsUpdates.updatePolicy)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.windowsUpdates.updatePolicy",
      "id": "a7aa99c1-34a2-850c-5223-7816fde70713",
      "complianceChangeRules": [
        {
          "@odata.type": "microsoft.graph.windowsUpdates.contentApprovalRule"
        }
      ],
      "createdDateTime": "String (timestamp)",
      "deploymentSettings": {
        "@odata.type": "microsoft.graph.windowsUpdates.deploymentSettings"
      },
      "autoEnrollmentUpdateCategories": [
        "String"
      ]
    }
  ]
}
```

