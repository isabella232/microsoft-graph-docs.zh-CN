---
title: stsPolicy 资源类型
description: 表示用于控制 Microsoft identity platform 行为的策略类型的抽象基类型。
localization_priority: Normal
author: lujiangfeng666
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: 078284cb4134b0b4fa2f86eb9a09f61ab6655351
ms.sourcegitcommit: 7ceec757fd82ef3fd80aa3089ef46d3807aa3aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48405279"
---
# <a name="stspolicy-resource-type"></a>stsPolicy 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示用于控制 [Microsoft identity platform](/azure/active-directory/develop/) 行为的策略类型的抽象基类型。

继承自 [policyBase](policyBase.md)。

## <a name="methods"></a>方法

无

## <a name="properties"></a>属性

| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|id|字符串| 此策略的唯一标识符。 只读。 继承自 [policyBase](policyBase.md)。|
|说明|字符串| 此策略的说明。 继承自 [policyBase](policyBase.md)。|
|displayName|字符串| 此策略的显示名称。 继承自 [policyBase](policyBase.md)。|
|定义|字符串集合| 一个字符串集合，其中包含定义策略的规则和设置的 JSON 字符串。 定义的语法因每个派生策略类型而异。 必需。|
|isOrganizationDefault|布尔|如果设置为 true，则激活此策略。 对于同一策略类型，可以有多个策略，但只有一个策略可以作为组织默认激活。 可选，默认值为 false。|

## <a name="relationships"></a>关系

无

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.stsPolicy",
  "baseType": "microsoft.graph.policyBase",
  "keyProperty": "id"
}-->

```json
{
  "id": "String (identifier)",
  "description": "String",
  "displayName": "String",
  "definition": ["String"],
  "isOrganizationDefault": true
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "stsPolicy resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->