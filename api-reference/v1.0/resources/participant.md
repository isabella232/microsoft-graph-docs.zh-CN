---
title: 参与者资源类型
description: 代表参与者类型。
author: ananmishr
localization_priority: Normal
ms.prod: cloud-communications
doc_type: resourcePageType
ms.openlocfilehash: 0c5004ea45cf44818c30ffe02dc48a1f6851e64a
ms.sourcegitcommit: d12bd5435c198bcd096e1f7f6a2716f4a04631cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2020
ms.locfileid: "48137112"
---
# <a name="participant-resource-type"></a>参与者资源类型

命名空间：microsoft.graph

表示呼叫中的参与者。

## <a name="methods"></a>方法

| 方法                                                 | 返回类型                                                 | 说明                                    |
|:-------------------------------------------------------|:------------------------------------------------------------|:-----------------------------------------------|
| [列出参与者](../api/participant-get.md)          | [参与者](participant.md)                               | 在呼叫中检索 **参与者** 对象的列表。 |
| [获取参与者](../api/participant-get.md)           | [参与者](participant.md)                               | 读取 **参与者** 对象的属性。 |
| [删除参与者](../api/participant-delete.md)         | 无   | 删除呼叫中的参与者。                  |
| [邀请](../api/participant-invite.md)                 | [inviteParticipantsOperation](../resources/inviteparticipantsoperation.md)                        | 邀请参与者加入呼叫。              |
| [参与者静音](../api/participant-mute.md)         | [muteParticipantOperation](muteparticipantoperation.md)     | 将呼叫中的参与者静音。                  |

## <a name="properties"></a>属性

| 属性             | 类型                                     | 说明                                                  |
| :------------------- | :--------------------------------------- | :------------------------------------------------------------|
| id                   | String                                   | 参与者 ID。                                          |
| info                 | [participantInfo](participantinfo.md)    | 参与者的参与者。                          |
| isInLobby            | Boolean                                  | `true` 如果参与者处于会议厅中。                          |
| isMuted              | Boolean                                  | `true` 如果与会者已静音 (客户端或服务器) 。    |
| mediaStreams         | [mediaStream](mediastream.md) 集合 | 媒体流的列表。                                   |
| recordingInfo        | [recordingInfo](recordinginfo.md)        | 有关参与者是否有录制功能的信息。 |

## <a name="relationships"></a>关系
无。

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.participant"
}-->
```json
{
  "id": "String (identifier)",
  "info": {"@odata.type": "#microsoft.graph.participantInfo"},
  "isInLobby": true,
  "isMuted": true,
  "mediaStreams": [ { "@odata.type": "#microsoft.graph.mediaStream" } ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "participant resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->

