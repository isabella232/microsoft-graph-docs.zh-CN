---
title: 创建 onPremisesAgentGroup
description: 创建新的 **onPremisesAgentGroup** 对象。
localization_priority: Normal
author: japere
ms.prod: microsoft-identity-platform
doc_type: apiPageType
ms.openlocfilehash: e8217451851d12916ce8fde2d287fa68b23c48c6
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48082209"
---
# <a name="create-onpremisesagentgroup"></a>创建 onPremisesAgentGroup

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

创建新的 [onPremisesAgentGroup](../resources/onpremisesagentgroup.md) 对象。

## <a name="permissions"></a>Permissions

要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

| 权限类型                        | 权限（从最低特权到最高特权） |
|:--------------------------------------|:---------------------------------------------------------|
|委派（工作或学校帐户）     | OnPremisesPublishingProfiles.ReadWrite.All |
| 委派（个人 Microsoft 帐户） | 不支持。 |
| 应用程序                            | 不支持。 |

## <a name="http-request"></a>HTTP 请求

<!-- { "blockType": "ignored" } -->

```http
POST ~/onPremisesPublishingProfiles/{publishingType}/agentGroups/{id}/agents
```

## <a name="request-headers"></a>请求标头

| 名称          | 说明   |
|:--------------|:--------------|
| Authorization | 持有者 {token} |

## <a name="request-body"></a>请求正文

在请求正文中，提供 [onPremisesAgentGroup](../resources/onpremisesagentgroup.md) 对象的 JSON 表示形式。

```json
{
    "displayName": "New Group"
}
```

## <a name="response"></a>响应

如果成功，此方法 `201 Created` 在响应正文中返回响应代码和 [onPremisesAgentGroup](../resources/onpremisesagentgroup.md) 对象。

## <a name="examples"></a>示例

### <a name="request"></a>请求

下面展示了示例请求。

# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_onpremisesagent_from_onpremisesagentgroup"
}-->

```http
POST https://graph.microsoft.com/beta/onPremisesPublishingProfiles/provisioning/agentGroups
```
# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-onpremisesagent-from-onpremisesagentgroup-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/create-onpremisesagent-from-onpremisesagentgroup-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


在请求正文中，提供 [onPremisesAgentGroup](../resources/onpremisesagentgroup.md) 对象的 JSON 表示形式。

```json
{
    "displayName": "New Group"
}
```

### <a name="response"></a>响应

下面展示了示例响应。

> **注意：** 为了提高可读性，可能缩短了此处显示的响应对象。所有属性都将通过实际调用返回。

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.onPremisesAgentGroup"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
    "id": "4655ed41-1619-4848-92bb-0576d3038682",
    "displayName": "New Group",
    "publishingType": "provisioning",
    "isDefault": false
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Create onPremisesAgent",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


