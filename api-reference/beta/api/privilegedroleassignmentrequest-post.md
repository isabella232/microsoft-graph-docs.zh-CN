---
title: 创建 privilegedRoleAssignmentRequest
description: 创建 privilegedroleassignmentrequest 对象。
localization_priority: Normal
doc_type: apiPageType
ms.prod: microsoft-identity-platform
author: shauliu
ms.openlocfilehash: f0405644cd2b7aebe71cef7f0594f8c5ec351e3e
ms.sourcegitcommit: 342516a52b69fcda31442b130eb6bd7e2c8a0066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48976191"
---
# <a name="create-privilegedroleassignmentrequest"></a>创建 privilegedRoleAssignmentRequest

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

创建 [privilegedroleassignmentrequest](../resources/privilegedroleassignmentrequest.md) 对象。

## <a name="permissions"></a>权限
要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

|权限类型                        | 权限（从最低特权到最高特权）              |
|:--------------------------------------|:---------------------------------------------------------|
|委派（工作或学校帐户） | PrivilegedAccess 的 AzureAD、Directory.accessasuser.all    |
|委派（个人 Microsoft 帐户） | 不支持。 |
|应用程序                            | 不支持。 |

## <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
```http
POST /privilegedRoleAssignmentRequests
```

## <a name="request-headers"></a>请求标头
| 名称      |说明|
|:----------|:----------|
| Authorization  | Bearer {token}。必需。 |

## <a name="request-body"></a>请求正文
在请求正文中，提供 [privilegedroleassignmentrequest](../resources/privilegedroleassignmentrequest.md) 对象的 JSON 表示形式。 

| 属性     | 类型    |  说明|
|:---------------|:--------|:----------|
|roleId|String|角色的 ID。 此为必需属性。|
|type|String|表示角色分配上的操作的类型。 值可以是 `AdminAdd` ： Administrators 将用户添加到角色; `UserAdd` ：用户添加角色分配。 必填。|
|assignmentState|String|工作分配的状态。 此值可 `Eligible` 用于符合条件的工作分配 `Active` -如果是由管理员直接分配的 `Active` ，或者是由用户的符合条件的工作分配激活的。 可取值为：``NotStarted``、`Completed`、`RequestedApproval`、`Scheduled`、`Approved`、`ApprovalDenied`、`ApprovalAborted`、`Cancelling`、`Cancelled`、`Revoked`、`RequestExpired`。 必填。|
|reason|String|需要为角色分配请求提供审核和审阅目的的原因。|
|schedule|[governanceSchedule](../resources/governanceschedule.md)|角色分配请求的日程安排。|

## <a name="response"></a>响应
如果成功，此方法 `201 Created` 在响应正文中返回响应代码和 [privilegedRoleAssignmentRequest](../resources/privilegedroleassignmentrequest.md) 对象。

### <a name="error-codes"></a>错误代码
此 API 返回该标准 HTTP 错误代码。 此外，它还可以返回下表中列出的错误代码。

|错误代码     | 错误消息              | 
|:--------------------| :---------------------|
| 400 BadRequest | RoleAssignmentRequest 属性为 NULL |
| 400 BadRequest | 无法反序列化 roleAssignmentRequest 对象。 |
| 400 BadRequest | RoleId 是必需的。 |
| 400 BadRequest | 必须指定计划开始日期，并且该日期应晚于现在。 |
| 400 BadRequest | 此用户、角色和计划类型的计划已存在。 |
| 400 BadRequest | 此用户、角色和审批类型已存在待批准的审批。 |
| 400 BadRequest | 请求者原因缺失。 |
| 400 BadRequest | 请求者原因不应超过500个字符。 |
| 400 BadRequest | 提升持续时间必须介于0.5 和 {from setting} 之间。 |
| 400 BadRequest | 计划激活和请求之间存在重叠。 |
| 400 BadRequest | 角色已激活。 |
| 400 BadRequest | GenericElevateUserToRoleAssignments： Tickting 信息是必需的，并且在激活过程中不提供。 |
| 400 BadRequest | 计划激活和请求之间存在重叠。 |
| 403未经授权 | 提升需要多因素身份验证。 |
| 403未经授权 | 代表提升是不允许的。 |

## <a name="example"></a>示例
##### <a name="request"></a>请求
下面展示了示例请求。

# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "post_privilegedroleassignmentrequest"
}-->
```http
POST https://graph.microsoft.com/beta/privilegedRoleAssignmentRequests
Content-type: application/json

{
    "duration": "2",
    "reason": "Activate the role for business purpose",
    "ticketNumber": "234",
    "ticketSystem": "system",
    "schedule": {
        "startDateTime": "2018-02-08T02:35:17.903Z"
    },
    "evaluateOnly": false,
    "type": "UserAdd",
    "assignmentState": "Active",
    "roleId": "88d8e3e3-8f55-4a1e-953a-9b9898b8876b"
}
```
# <a name="c"></a>[C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/post-privilegedroleassignmentrequest-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/post-privilegedroleassignmentrequest-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/post-privilegedroleassignmentrequest-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="java"></a>[Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/post-privilegedroleassignmentrequest-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

##### <a name="response"></a>响应
下面是一个响应示例。 注意：为简洁起见，可能会截断此处显示的响应对象。 将从实际调用中返回所有属性。
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.privilegedRoleAssignmentRequest"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 304


{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#privilegedRoleAssignmentRequests/$entity",
    "schedule": {
        "type": "activation",
        "startDateTime": "2018-02-08T02:35:17.903Z",
        "endDateTime": null,
        "duration" : null
    },
    "id": "e13ef8a0-c1cb-4d03-aaae-9cd1c8ede2d1",
    "evaluateOnly": false,
    "type": "UserAdd",
    "assignmentState": "Active",
    "requestedDateTime": "2018-02-08T02:35:42.9137335Z",
    "status": "NotStarted",
    "duration": "2",
    "reason": "Activate the role for business purpose",
    "ticketNumber": "234",
    "ticketSystem": "system",
    "userId": "Self",
    "roleId": "88d8e3e3-8f55-4a1e-953a-9b9898b8876b"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Post privilegedRoleAssignmentRequest",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->


