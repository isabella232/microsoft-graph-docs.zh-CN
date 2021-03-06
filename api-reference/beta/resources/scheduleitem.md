---
title: scheduleItem 资源类型
description: 一个项目，该项目描述与用户的默认日历上的实际事件相对应的用户的可用性。 此项也适用于资源。
localization_priority: Normal
doc_type: resourcePageType
ms.prod: microsoft-teams
author: harini84
ms.openlocfilehash: 9c7ed4d1683a4b6f45161db5304d70dce17d0dd4
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47985804"
---
# <a name="scheduleitem-resource-type"></a>scheduleItem 资源类型

命名空间：microsoft.graph

 [!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

一个项目，该项目描述与用户的默认日历上的实际事件相对应的用户的可用性。 此项也适用于资源 (会议室或设备) 。

## <a name="properties"></a>属性
| 属性     | 类型   |说明|
|:---------------|:--------|:----------|
|end |[dateTimeTimeZone](datetimetimezone.md) |相应事件结束时的日期、时间和时区。 |
|isPrivate |Boolean |相应事件的敏感度。 如果已标记事件，则为 True `private` ，否则为 false。 可选。 |
|位置 |String | 保留或参与的相应事件的位置。 可选。|
|start |[dateTimeTimeZone](datetimetimezone.md) |相应事件的开始日期、时间和时区。 |
|状态 |freeBusyStatus | 相应事件期间用户或资源的可用性状态。 可能的值包括 `free`、`tentative`、`busy`、`oof`、`workingElsewhere`、`unknown`。 |
|subject |String | 相应事件的主题行。 可选。|


## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "isPrivate",
    "location",
    "subject"
  ],
  "@odata.type": "microsoft.graph.scheduleItem"
}-->

```json
{
  "end": {"@odata.type": "microsoft.graph.dateTimeTimeZone"},
  "isPrivate": true,
  "location": "String",
  "start": {"@odata.type": "microsoft.graph.dateTimeTimeZone"},
  "status": "String",
  "subject": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "scheduleItem resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


