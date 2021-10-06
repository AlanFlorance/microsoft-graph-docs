---
title: "Get file"
description: "Read the properties and relationships of a file object."
ms.localizationpriority: medium
author: "mahage-msft"
ms.prod: "ediscovery"
doc_type: "apiPageType"
---

# Get file
Namespace: microsoft.graph.ediscovery

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [file](../resources/ediscovery-file.md) object.

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
GET /compliance/ediscovery/cases/{caseId}/reviewSets/{reviewSetId}/files/{fileId}
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

If successful, this method returns a `200 OK` response code and a [file](../resources/ediscovery-file.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "get_file"
}
-->
``` http
GET https://graph.microsoft.com/beta/compliance/ediscovery/cases/{caseId}/reviewSets/{reviewSetId}/files/{fileId}
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.ediscovery.file"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.ediscovery.file",
    "id": "319d9a1e-9a1e-319d-1e9a-9d311e9a9d31",
    "date": "String (timestamp)",
    "size": "Integer",
    "name": "String",
    "sourceType": "String",
    "senderAuthor": [
      "String"
    ],
    "subjectTitle": "String",
    "extension": "String",
    "mediaType": "String",
    "processingStatus": "String",
    "content": "Stream",
    "extractedTextContent": "String",
    "otherProperties": {
      "@odata.type": "microsoft.graph.ediscovery.stringValueDictionary"
    }
  }
}
```
