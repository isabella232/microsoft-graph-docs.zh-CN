---
title: securityActionState 资源类型
description: 表示 securityAction 状态更改的历史记录。
localization_priority: Normal
author: preetikr
ms.prod: security
doc_type: resourcePageType
ms.openlocfilehash: ba22a03f4d4a6d03b0093ed28b8c54a7c095d037
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47988861"
---
# <a name="securityactionstate-resource-type"></a>securityActionState 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示 securityAction 状态更改的历史记录。

## <a name="properties"></a>属性

| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|appId|String|向操作提交更新 (PATCH) 的调用应用程序的应用程序 ID。 `appId`应从 auth 令牌中提取，而不是通过调用应用程序手动输入。|
|状态|String| 此更新中的 securityAction 的状态。 可取值为：`NotStarted`、`Running`、`Completed`、`Failed`。|
|updatedDateTime|DateTimeOffset| 更新 actionState 时的时间戳。 时间戳类型表示采用 ISO 8601 格式的日期和时间信息，始终采用 UTC 时区。 例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`|
|user|String|向操作提交更新 (PATCH) 的已登录用户的用户主体名称。 `user`应从 auth 令牌中提取，而不是通过调用应用程序手动输入。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.securityActionState",
  "baseType": null
}-->

```json
{
  "appId": "String",
  "status": "String",
  "updatedDateTime": "String (timestamp)",
  "user": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "securityActionState resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


