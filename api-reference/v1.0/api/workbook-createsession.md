---
title: 工作簿： createSession
description: 创建新的工作簿会话。
author: lumine2008
localization_priority: Normal
ms.prod: excel
doc_type: apiPageType
ms.openlocfilehash: a7b021173b28826642898d96c889a955f8bd182e
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47970899"
---
# <a name="workbook-createsession"></a>工作簿： createSession

命名空间：microsoft.graph

创建新的工作簿会话。 

可以在以下任一模式下调用 Excel API： 

1. 永久会话 - 保持（保存）对工作簿所做的全部更改。这是常用的操作模式。 
2. 非永久会话 - 不会将 API 所做的更改保存到源位置。相反，Excel 后端服务器保留文件的临时副本，体现在特定 API 会话期间所做的更改。Excel 会话过期时，这些更改将丢失。此模式可用于需要进行分析或获得计算结果或图表图像的应用，但不会影响文档状态。   

若要表示 API 中的会话，请使用 `workbook-session-id: {session-id}` 标头。 

>**注意：** Excel API 不需要会话标头也能起作用。但是，建议你使用会话标头来提高性能。如果不使用会话标头，API 调用过程中进行的更改_仅_保持在该文件中。  

在某些情况下，创建新的会话需要不确定的时间才能完成。 Microsoft Graph 还提供了长时间运行的操作模式。 此模式提供了一种方法来轮询创建状态更新，而无需等待创建完成。 步骤如下：

1. 向 `Prefer: respond-async` 请求中添加一个标头，以指示它是一个长时间运行的操作。
2. 响应返回一个 `Location` 标头，以指定用于轮询创建操作状态的 URL。 您可以通过访问指定的 URL 来获取操作状态。 状态将为以下之一： `notStarted` 、、 `running` `succeeded` 或 `failed` 。
3. 操作完成后，可以再次请求状态，响应将显示为 `succeeded` 或 `failed` 。

## <a name="error-handling"></a>错误处理

此请求有时可能会收到 504 HTTP 错误。 此错误的适当响应做法是重复发出请求。

## <a name="permissions"></a>权限
要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

|权限类型      | 权限（从最低特权到最高特权）              |
|:--------------------|:---------------------------------------------------------|
|委派（工作或学校帐户） | Files.ReadWrite    |
|委派（个人 Microsoft 帐户） | 不支持。    |
|应用程序 | 不支持。 |

## <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
```http
POST /workbook/createSession
```
## <a name="request-headers"></a>请求标头
| 名称       | 说明|
|:---------------|:----------|
| Authorization  | Bearer {token}。必需。 |

## <a name="request-body"></a>请求正文
在请求正文中，提供 [workbookSessionInfo](../resources/workbooksessioninfo.md) 对象的 JSON 表示形式。

## <a name="response"></a>响应

如果成功，此方法 `201 Created` 在响应正文中返回响应代码和 [workbookSessionInfo](../resources/workbooksessioninfo.md) 对象。 对于长时间运行的操作，它会 `202 Accepted ` 在响应中返回响应代码和 `Location` 标头，其中包含空正文。

## <a name="examples"></a>示例

### <a name="example-1-basic-session-creation"></a>示例1：基本会话创建
#### <a name="request"></a>请求


# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_excel_session"
}-->
```http
POST https://graph.microsoft.com/v1.0/me/drive/items/{id}/workbook/createSession
Content-type: application/json
Content-length: 52

{
  "persistChanges": true
}
```
# <a name="c"></a>[C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-excel-session-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-excel-session-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/create-excel-session-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="java"></a>[Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-excel-session-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### <a name="response"></a>响应
>**注意：** 为了提高可读性，可能缩短了此处显示的响应对象。 
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.workbookSessionInfo"
} -->
```http
HTTP/1.1 201 Created
Content-type: application/json
Content-length: 52

{
  "id": "id-value",
  "persistChanges": true
}
```

### <a name="example-2-session-creation-with-long-running-operation-pattern"></a>示例2：使用长时间运行的操作模式创建的会话

#### <a name="request"></a>请求

```http
POST https://graph.microsoft.com/v1.0/me/drive/items/{drive-item-id}/workbook/worksheets({id})/createSession
Prefer: respond-async
Content-type: application/json
{
    "persistChanges": true
}
```

#### <a name="response"></a>响应
>**注意：** 为了提高可读性，可能缩短了此处显示的响应对象。 

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.workbookSessionInfo"
} -->
```http
HTTP/1.1 202 Accepted
Location: https://graph.microsoft.com/v1.0/me/drive/items/{drive-item-id}/workbook/operations/{operation-id}
Content-type: application/json
{
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79 
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Example",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->

