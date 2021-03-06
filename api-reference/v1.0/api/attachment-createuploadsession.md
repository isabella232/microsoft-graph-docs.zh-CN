---
title: 附件： createUploadSession
description: 创建上载会话以以迭代方式上载文件的范围，以便将文件附加到指定的邮件。
localization_priority: Normal
author: svpsiva
ms.prod: outlook
doc_type: apiPageType
ms.openlocfilehash: 6586842b36b89dda6cb5c501a85038f35feee318
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48046032"
---
# <a name="attachment-createuploadsession"></a>附件： createUploadSession

命名空间：microsoft.graph

创建一个允许应用程序以迭代方式上载文件范围的上载会话，以便将该文件附加到指定的 Outlook 项目。 项目可以是 [消息](../resources/message.md) 或 [事件](../resources/event.md)。

如果文件大小在 3 MB 到 150 MB 之间，则使用此方法附加文件。 若要附加小于 3 MB 的文件，请 `POST` 在 Outlook 项目的 " **附件** " 导航属性上执行操作; 请参阅如何为 [邮件](message-post-attachments.md) 或 [事件](event-post-attachments.md)执行此操作。 

作为响应的一部分，此操作将返回可在后续顺序查询中使用的上载 URL `PUT` 。 每个操作的请求标头 `PUT` 允许您指定要上载的确切字节范围。 这样，如果在上载过程中断开网络连接，则可以恢复传输。 

以下是使用上载会话将文件附加到 Outlook 项目的步骤：

1. 创建上传会话。
2. 在该上传会话中，在每次) 上载文件的所有字节，并将该文件附加到指定的项目中时，会在每次重复上载的字节范围 (最大为 4 MB。
3. 保存附件的 ID 以供将来访问。
4. 可选：删除上传会话。

有关示例，请参阅 [将大型文件附加到 Outlook 消息或事件](/graph/outlook-large-attachments) 。

> [!TIP]
> Exchange Online 允许管理员自定义 Microsoft 365 邮箱的邮件大小限制，包括任何邮件附件。 默认情况下，此邮件大小限制为 35 MB。 了解如何 [自定义最大邮件大小](https://www.microsoft.com/microsoft-365/blog/2015/04/15/office-365-now-supports-larger-email-messages-up-to-150-mb) ，以支持大于租户默认限制的附件。 

> [!IMPORTANT] 
> 如果要将大型文件附加到共享或委派邮箱中的邮件或事件，请注意 [已知问题](/graph/known-issues#attaching-large-files-to-messages) 。

## <a name="permissions"></a>权限

要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

| 权限类型                        | 权限（从最低特权到最高特权） |
|:---------------------------------------|:--------------------------------------------|
| 委派（工作或学校帐户）     | "日历"、"邮件"、"写" |
| 委派（个人 Microsoft 帐户） | "日历"、"邮件"、"写" |
| 应用程序                            | "日历"、"邮件"、"写" |

## <a name="http-request"></a>HTTP 请求

创建用于将文件附加到 **事件**的上载会话： 

<!-- { "blockType": "ignored" } -->
```http
POST /me/events/{id}/attachments/createUploadSession
```

创建用于将文件附加到 **邮件**的上载会话： 

<!-- { "blockType": "ignored" } -->
```http
POST /me/messages/{id}/attachments/createUploadSession
```

## <a name="request-headers"></a>请求标头

| 名称          | 说明   |
|:--------------|:--------------|
| Authorization | 持有者 {token} |


## <a name="request-body"></a>请求正文

在请求正文中，提供具有以下参数的 JSON 对象。

| 参数    | 类型        | 说明 |
|:-------------|:------------|:------------|
|AttachmentItem|[attachmentItem](../resources/attachmentitem.md)|表示要上载和附加的项的属性。 至少要指定附件类型 (`file`) 、名称和文件大小。|

## <a name="response"></a>响应

如果成功，此方法 `201 Created` 在响应正文中返回响应代码和新的 [uploadSession](../resources/uploadsession.md) 对象。

>**注意**： 
>
>作为**uploadSession** response 对象的一部分返回的**uploadUrl**属性是一个不透明的 URL，用于随后的 `PUT` 查询上传文件的字节范围。 它包含针对 ExpirationDateTime 到期的后续查询的相应 auth 令牌 `PUT` 。 **expirationDateTime** 请勿自定义此 URL。
>
>**NextExpectedRanges**属性指定要从中上载的下一个文件字节位置，例如 `"NextExpectedRanges":["2097152"]` 。 必须按顺序上传文件中的字节。

<!-- The **nextExpectedRanges** property specifies one or more ranges of bytes that the server is still missing for the file. These ranges are zero-indexed and of the format `{start}-{end}`, unless if the server misses the remainder of the bytes from the start of that range, in which case the format is simply `{start}`.  -->


## <a name="examples"></a>示例

下面的示例演示如何创建可在后续文件上载操作中用于指定邮件的上载会话。

### <a name="request"></a>请求


# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "attachment_createuploadsession",
  "sampleKeys": ["AAMkADI5MAAIT3drCAAA="]
}-->

```http
POST https://graph.microsoft.com/v1.0/me/messages/AAMkADI5MAAIT3drCAAA=/attachments/createUploadSession
Content-type: application/json

{
  "AttachmentItem": {
    "attachmentType": "file",
    "name": "flower", 
    "size": 3483322
  }
}
```
# <a name="c"></a>[C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/attachment-createuploadsession-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/attachment-createuploadsession-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/attachment-createuploadsession-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="java"></a>[Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/attachment-createuploadsession-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### <a name="response"></a>响应

> **注意：** 为了提高可读性，可能缩短了此处显示的响应对象。所有属性都将通过实际调用返回。

<!-- {
  "blockType": "response",
  "name": "attachment_createuploadsession",
  "truncated": true,
  "@odata.type": "microsoft.graph.uploadSession"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#microsoft.graph.uploadSession",
    "uploadUrl": "https://outlook.office.com/api/v1.0/Users('a8e8e219-4931-95c1-b73d-62626fd79c32@72aa88bf-76f0-494f-91ab-2d7cd730db47')/Messages('AAMkADI5MAAIT3drCAAA=')/AttachmentSessions('AAMkADI5MAAIT3k0uAAA=')?authtoken=eyJhbGciOiJSUzI1NiIsImtpZCI6IktmYUNIUlN6bllHMmNI",
    "expirationDateTime": "2019-09-25T01:09:30.7671707Z",
    "nextExpectedRanges": [
        "0-"
    ]
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "attachment: createUploadSession",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

