---
title: 列出 applicationTemplates
description: 检索 applicationtemplate 对象的列表。
localization_priority: Normal
author: luleonpla
ms.prod: microsoft-identity-platform
doc_type: apiPageType
ms.openlocfilehash: 0f50d8bf63b58ec5b1aad0e0318ad72314dda7ec
ms.sourcegitcommit: 342516a52b69fcda31442b130eb6bd7e2c8a0066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48961708"
---
# <a name="list-applicationtemplates"></a>列出 applicationTemplates

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

从 Azure AD 应用程序库中检索 [applicationTemplate](../resources/applicationtemplate.md) 对象的列表。

## <a name="permissions"></a>权限

要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

| 权限类型                        | 权限（从最低特权到最高特权） |
|:---------------------------------------|:--------------------------------------------|
| 委派（工作或学校帐户）     | 无。 |
| 委派（个人 Microsoft 帐户） | 不支持。 |
| 应用程序                            | 无。 |

只要您的应用程序具有有效的访问令牌以调用 Microsoft Graph，就不需要额外的权限即可调用此 API。

## <a name="http-request"></a>HTTP 请求

<!-- { "blockType": "ignored" } -->

```http
GET /applicationTemplates
```

## <a name="optional-query-parameters"></a>可选的查询参数

此方法支持一些 OData 查询参数来帮助自定义响应。 

- 您可以 `$filter` 在有限的方式中使用该参数。 只能按 **displayName** 或 **类别** 进行筛选。 例如， `$filter=contains(displayName, 'salesf')` 或 `$filter=categories/any(c:contains(c, 'myCategory'))`。
- 可以 `$orderby` `$top,` `$skip` 在任何 GET 请求中使用和查询参数。

若要了解一般信息，请参阅 [OData 查询参数](/graph/query-parameters)。

## <a name="request-headers"></a>请求标头

| 名称      |说明|
|:----------|:----------|
| Authorization | Bearer {code} |

## <a name="request-body"></a>请求正文

请勿提供此方法的请求正文。

## <a name="response"></a>响应

如果成功，此方法 `200 OK` 在响应正文中返回响应代码和 [applicationTemplate](../resources/applicationtemplate.md) 对象集合。

## <a name="examples"></a>示例

### <a name="request"></a>请求

下面展示了示例请求。

# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_applicationtemplates"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/applicationTemplates
```
# <a name="c"></a>[C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-applicationtemplates-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-applicationtemplates-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/get-applicationtemplates-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="java"></a>[Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-applicationtemplates-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### <a name="response"></a>响应

下面展示了示例响应。

> [!NOTE]
> 为了提高可读性，可能缩短了此处显示的响应对象。 所有属性都将通过实际调用返回。

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.applicationTemplate",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": [
    {
      "id" : "id-value",
      "displayName" : "displayName-value",
      "homePageUrl" : "homePageUrl-value",
      "supportedSingleSignOnModes" : ["supportedSingleSignOnModes-value"],
      "logoUrl" : "logoUrl-value",
      "categories" : ["categories-value"],
      "publisher" : "publisher-value",
      "description" : "description-value"
    }
  ]
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List applicationTemplates",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


