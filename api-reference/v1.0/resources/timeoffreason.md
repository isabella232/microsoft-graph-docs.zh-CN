---
title: timeOffReason 资源类型
description: 表示在计划中花费时间的有效原因。
author: akumar39
localization_priority: Normal
ms.prod: microsoft-teams
doc_type: resourcePageType_
ms.openlocfilehash: 1630cf2c76ca98f8637af9c80900daf97bcc5660
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48090786"
---
# <a name="timeoffreason-resource-type"></a>timeOffReason 资源类型

命名空间：microsoft.graph

表示对[计划](schedule.md)中的[timeOff](timeoff.md)实例的有效原因。

## <a name="methods"></a>方法

| 方法       | 返回类型  |Description|
|:---------------|:--------|:----------|
|[List](../api/schedule-list-timeoffreasons.md) | [timeOffReason](timeoffreason.md) 集合 | 获取计划中的 **timeOffReason** 列表。|
|[Create](../api/schedule-post-timeoffreasons.md) | [timeOffReason](timeoffreason.md) | 创建新的 **timeOffReason**。|
|[Get](../api/timeoffreason-get.md) | [timeOffReason](timeoffreason.md) | 按 ID 获取 **timeOffReason** 。|
|[Replace](../api/timeoffreason-put.md) | [timeOffReason](timeoffreason.md) | 替换 **timeOffReason**。|
|[删除](../api/timeoffreason-delete.md) | 无 | 将 **timeOffReason** 标记为非活动状态。|

## <a name="properties"></a>属性
|名称          |类型           |说明                                                                                 |
|--------------|---------------|--------------------------------------------------------------------------------------------|
| id            |`string`      |`timeOffReason` 的 ID。|
| displayName               | `string`                  | **TimeOffReason**的名称。 必需。 |
| iconType | `timeOffReasonIconType`   | 支持的图标类型：无;car式运行planefirstAid;dr.notWorking;构造juryDuty;投放cup of电话气候防护piggyBank;监控桩trafficCone;针sunny. 必需。 |
| isActive          |`Boolean`      | 指示在创建新实体或更新现有实体时是否可以使用 **timeOffReason** 。 必需。 |
| createdDateTime       |`DateTimeOffset`        |首次创建此 **timeOffReason** 的时间戳。 时间戳类型表示采用 ISO 8601 格式的日期和时间信息，始终采用 UTC 时间。 例如，2014 年 1 月 1 日午夜 (UTC) 如下所示：“2014-01-01T00:00:00Z”。 |
| lastModifiedDateTime      |`DateTimeOffset`         |上次更新此 **timeOffReason** 的时间戳。 时间戳类型表示采用 ISO 8601 格式的日期和时间信息，始终采用 UTC 时间。 例如，2014 年 1 月 1 日午夜 (UTC) 如下所示：“2014-01-01T00:00:00Z”。 |
| lastModifiedBy        | [identitySet](identityset.md)        |上次更新此 **timeOffReason**的标识。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.timeOffReason",
  "baseType":"microsoft.graph.changeTrackedEntity"
}-->

```json
{
  "id": "String",
  "createdDateTime": "String (timestamp)",
  "lastModifiedDateTime": "String (timestamp)",
  "displayName": "String",
  "iconType": "String",
  "isActive": true,
  "lastModifiedBy": { "@odata.type":"microsoft.graph.identitySet"}
}
```


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "timeOffReason resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->

