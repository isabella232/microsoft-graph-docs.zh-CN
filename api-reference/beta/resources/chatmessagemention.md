---
title: chatMessageMention 资源类型
description: '表示了 chatmessage 实体中提及的项。 提及可用于用户、团队、机器人或频道。 '
localization_priority: Normal
author: nkramer
ms.prod: microsoft-teams
doc_type: resourcePageType
ms.openlocfilehash: b6a63380475be8bd0e669851f7e760a9f645d18d
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48064275"
---
# <a name="chatmessagemention-resource-type"></a>chatMessageMention 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示 [了 chatmessage](chatmessage.md) 实体中提及的项。 提及可用于 [用户](user.md)、 [团队](team.md)、机器人或 [频道](channel.md)。 

在包含一个或多个提及的 **了 chatmessage** 对象中，邮件正文 **内容** 属性代表 HTML 中的聊天消息。 它将每个提及的 **mentionText** 封装在 HTML `at` 元素中，其中包含一个与 `id` 提及的 **id** 属性相对应的属性。

例如，聊天邮件包含两个提及，分别提及 "Megan" 和 "Alex" 文本。 其 body **内容** 属性按 `at` 如下所示为两个提及指定元素：

``` json
"body": {
    "contentType": "html",
    "content": "<div><div>Ah, <at id=\"0\">Megan</at>, <at id=\"1\">Alex</at>, I saw them in a separate folder. Thanks!</div>\n</div>"
}
```

在 **content** 属性中，第一个提及的 HTML `id` 属性为0。 这对应于**chatMessageMention**的第一个实例的**id**属性，也是0。

第二个提及的 `id` 属性为1，与第二个实例的 **id** 属性相匹配，即1。

有关此示例的更完整上下文，请参阅 [列出通道邮件答复](../api/channel-list-messagereplies.md#example)。

## <a name="properties"></a>属性
| 属性     | 类型   |说明|
|:---------------|:--------|:----------|
|id|Int32|在指定的 **了 chatmessage**中提到的实体的索引。 与邮件正文中对应的标记中的 {index} 值相匹配 `<at id="{index}">` 。|
|mentionText|string|用于表示提及的字符串。 例如，用户的显示名称（团队名称）。|
|所|[identitySet](identityset.md)|实体 (提到的用户、应用程序、团队或频道) 。  如果它是 @mentioned 的频道或团队，则了解 identityset 包含一个 **会话** 属性，该属性提供团队/通道的 ID 和代表团队或频道的 **conversationIdentityType** 属性。|


## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.chatMessageMention"
}-->

```json
{
  "id": 1024,
  "mentionText": "string",
  "mentioned": {"@odata.type": "microsoft.graph.identitySet"}
 }
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "chat mention resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


