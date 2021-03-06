---
title: signInStatus 资源类型
description: 提供登录状态 (成功或失败) 登录
localization_priority: Normal
doc_type: resourcePageType
ms.prod: ''
author: SarahBar
ms.openlocfilehash: 339041f4fa332efdf949ed5d3c4cad1ad6fdcf2c
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48067112"
---
# <a name="signinstatus-resource-type"></a>signInStatus 资源类型

命名空间： microsoft. graph 提供登录状态 (成功或失败) 登录



## <a name="properties"></a>属性
| 属性     | 类型   |说明|
|:---------------|:--------|:----------|
|additionalDetails|String|提供有关登录活动的其他详细信息|
|errorCode|Int32|提供在登录失败过程中生成的 5-6digit 错误代码。 查看 [错误代码和消息的列表](/azure/active-directory/active-directory-reporting-activity-sign-ins-errors)。|
|failureReason|String|为相应的登录活动提供错误消息或失败原因。 查看 [错误代码和消息的列表](/azure/active-directory/active-directory-reporting-activity-sign-ins-errors)。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.signInStatus"
}-->

```json
{
  "additionalDetails": "String",
  "errorCode": 1024,
  "failureReason": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "signInStatus resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


