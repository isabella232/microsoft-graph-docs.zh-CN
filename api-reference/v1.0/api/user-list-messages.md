---
title: List messages
description: 获取登录用户的邮箱（包括“已删除邮件”和“待筛选邮件”文件夹）中的邮件。
localization_priority: Priority
author: svpsiva
ms.prod: outlook
doc_type: apiPageType
ms.openlocfilehash: 8929394f3b7f0e315652bdc25762a607c28f7acf
ms.sourcegitcommit: 21481acf54471ff17ab8043b3a96fcb1d2f863d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48634849"
---
# <a name="list-messages"></a>列出邮件

命名空间：microsoft.graph

获取登录用户的邮箱（包括“已删除邮件”和“待筛选邮件”文件夹）中的邮件。

根据页面大小和邮箱数据，从邮箱中获取邮件可能会引发多个请求。 默认页面大小为 10 封邮件。 若要获取下一页的邮件，只需将 `@odata.nextLink` 中返回的整个 URL 应用于下一个 get-messages 请求。 此 URL 包括可能已在初始请求中指定的任何查询参数。 

不要尝试从 `@odata.nextLink` URL 中提取 `$skip` 值来操纵响应。 此 API 使用 `$skip` 值来保留其已在用户邮箱中遍历的所有项的计数，以返回 message-type 项的页面。 因此，甚至在初始响应中，`$skip` 值都会大于页面大小。 有关详细信息，请参阅[在应用中对 Microsoft Graph 数据进行分页](/graph/paging)。

目前，此操作返回纯 HTML 格式的邮件正文。

在以下两种情况下，应用可以获取其他用户的邮件文件夹中的邮件：

* 如果该应用具有应用程序权限，或者
* 如果应用具有来自某个用户的相应委派[权限](#permissions)，而另一个用户与该用户共享了邮件文件夹，或者已为该用户授予委派的访问权限。 请参阅[详细信息和示例](/graph/outlook-share-messages-folders)。

> **注意**：请注意[已知问题](/graph/known-issues#get-messages-returns-chats-in-microsoft-teams)，即此操作在自己的响应中包含 Microsoft Teams 聊天消息。

## <a name="permissions"></a>权限
要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

|权限类型      | 权限（从最低特权到最高特权）              |
|:--------------------|:---------------------------------------------------------|
|委派（工作或学校帐户） | Mail.ReadBasic、Mail.Read、Mail.ReadWrite    |
|委派（个人 Microsoft 帐户） | Mail.ReadBasic、Mail.Read、Mail.ReadWrite    |
|应用程序 | Mail.ReadBasic.All、Mail.Read、Mail.ReadWrite |

## <a name="http-request"></a>HTTP 请求

若要获取用户邮箱中的所有邮件，请执行以下操作：

<!-- { "blockType": "ignored" } -->
```http
GET /me/messages
GET /users/{id | userPrincipalName}/messages
```

若要获取用户邮箱中特定文件夹中的邮件，请执行以下操作：

<!-- { "blockType": "ignored" } -->
```http
GET /me/mailFolders/{id}/messages
GET /users/{id | userPrincipalName}/mailFolders/{id}/messages
```

## <a name="optional-query-parameters"></a>可选的查询参数
此方法支持 [OData 查询参数](/graph/query-parameters) 来帮助自定义响应。

### <a name="using-filter-and-orderby-in-the-same-query"></a>在同一查询中使用 filter 和 orderby
在同一查询中使用 `$filter` 和 `$orderby` 获取消息时，请确保按以下方式指定属性：

1. `$orderby` 中显示的属性也必须在 `$filter` 中显示。 
2. `$orderby` 中显示的属性与 `$filter` 中属性的顺序相同。
3. `$orderby` 中存在的属性显示在 `$filter` 中不存在的任意属性之前。

无法进行此项操作时会导致下列错误：

- 错误代码：`InefficientFilter`
- 错误消息：`The restriction or sort order is too complex for this operation.`

## <a name="request-headers"></a>请求标头
| 名称       | 类型 | 说明|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer {token}。必需。 |
| Prefer: outlook.body-content-type | string | 要返回的 **body** 和 **uniqueBody** 属性的格式。 可取值为“text”或“html”。 如果未指定此头，采用 HTML 格式返回 **body** 和 **uniqueBody** 属性。 可选。 |


## <a name="request-body"></a>请求正文
请勿提供此方法的请求正文。

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 `200 OK` 响应代码和 [Message](../resources/message.md) 对象集合。

## <a name="example"></a>示例
##### <a name="request"></a>请求
此示例获取已登录用户的邮箱中的默认前 10 封邮件。 它使用 `$select` 在响应中返回每封邮件的属性的子集。

# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_messages"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/me/messages?$select=sender,subject
```
# <a name="c"></a>[C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-messages-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-messages-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/get-messages-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="java"></a>[Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-messages-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

##### <a name="response"></a>响应
下面是一个响应示例。 若要获取下一页邮件，请将 `@odata.nextLink` 中返回的 URL 应用 于后续 GET 请求。

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.message",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('bb8775a4-4d8c-42cf-a1d4-4d58c2bb668f')/messages(sender,subject)",
    "@odata.nextLink": "https://graph.microsoft.com/v1.0/me/messages?$select=sender%2csubject&$skip=14",
    "value": [
        {
            "@odata.etag": "W/\"CQAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAwR4Hg\"",
            "id": "AAMkAGUAAAwTW09AAA=",
            "subject": "You have late tasks!",
            "sender": {
                "emailAddress": {
                    "name": "Microsoft Planner",
                    "address": "noreply@Planner.Office365.com"
                }
            }
        },
        {
            "@odata.etag": "W/\"CQAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4D1e\"",
            "id": "AAMkAGUAAAq5QKlAAA=",
            "subject": "You have late tasks!",
            "sender": {
                "emailAddress": {
                    "name": "Microsoft Planner",
                    "address": "noreply@Planner.Office365.com"
                }
            }
        },
        {
            "@odata.etag": "W/\"CQAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4D0v\"",
            "id": "AAMkAGUAAAq5QKkAAA=",
            "subject": "Your Azure AD Identity Protection Weekly Digest",
            "sender": {
                "emailAddress": {
                    "name": "Microsoft Azure",
                    "address": "azure-noreply@microsoft.com"
                }
            }
        },
        {
            "@odata.etag": "W/\"CQAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4DsN\"",
            "id": "AAMkAGUAAAq5QKjAAA=",
            "subject": "Use attached file",
            "sender": {
                "emailAddress": {
                    "name": "Megan Bowen",
                    "address": "MeganB@contoso.OnMicrosoft.com"
                }
            }
        },
        {
            "@odata.etag": "W/\"CQAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4Dq9\"",
            "id": "AAMkAGUAAAq5QKiAAA=",
            "subject": "Original invitation",
            "sender": {
                "emailAddress": {
                    "name": "Megan Bowen",
                    "address": "MeganB@contoso.OnMicrosoft.com"
                }
            }
        },
        {
            "@odata.etag": "W/\"CQAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4Dq1\"",
            "id": "AAMkAGUAAAq5QKhAAA=",
            "subject": "Koala image",
            "sender": {
                "emailAddress": {
                    "name": "Megan Bowen",
                    "address": "MeganB@contoso.OnMicrosoft.com"
                }
            }
        },
        {
            "@odata.etag": "W/\"CQAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4Dqp\"",
            "id": "AAMkAGUAAAq5QKgAAA=",
            "subject": "Sales invoice template",
            "sender": {
                "emailAddress": {
                    "name": "Megan Bowen",
                    "address": "MeganB@contoso.OnMicrosoft.com"
                }
            }
        },
        {
            "@odata.type": "#microsoft.graph.eventMessage",
            "@odata.etag": "W/\"DAAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4Dft\"",
            "id": "AAMkAGUAAAq5UMVAAA=",
            "subject": "Accepted: Review strategy for Q3",
            "sender": {
                "emailAddress": {
                    "name": "Adele Vance",
                    "address": "/O=EXCHANGELABS/OU=EXCHANGE ADMINISTRATIVE GROUP (FYDIBOHF23SPDLT)/CN=RECIPIENTS/CN=A17A02BCF30C4937A87B14273385667C-ADELEV"
                }
            }
        },
        {
            "@odata.type": "#microsoft.graph.eventMessage",
            "@odata.etag": "W/\"DAAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4DfF\"",
            "id": "AAMkAGUAAAq5UMUAAA=",
            "subject": "Accepted: Review strategy for Q3",
            "sender": {
                "emailAddress": {
                    "name": "Adele Vance",
                    "address": "/O=EXCHANGELABS/OU=EXCHANGE ADMINISTRATIVE GROUP (FYDIBOHF23SPDLT)/CN=RECIPIENTS/CN=A17A02BCF30C4937A87B14273385667C-ADELEV"
                }
            }
        },
        {
            "@odata.type": "#microsoft.graph.eventMessage",
            "@odata.etag": "W/\"CwAAABYAAADHcgC8Hl9tRZ/hc1wEUs1TAAAq4Dfa\"",
            "id": "AAMkAGUAAAq5T8tAAA=",
            "subject": "Review strategy for Q3",
            "sender": {
                "emailAddress": {
                    "name": "Megan Bowen",
                    "address": "MeganB@contoso.OnMicrosoft.com"
                }
            }
        }
    ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List messages",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
