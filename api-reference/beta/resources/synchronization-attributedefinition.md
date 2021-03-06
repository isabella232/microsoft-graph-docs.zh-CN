---
title: attributeDefinition 资源类型
description: 描述对象的属性。
localization_priority: Normal
doc_type: resourcePageType
author: ArvindHarinder1
ms.prod: microsoft-identity-platform
ms.openlocfilehash: 4d8a911b7f6ab3b916515eb73d53bfaf489047e0
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48078088"
---
# <a name="attributedefinition-resource-type"></a>attributeDefinition 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

描述对象的属性。

## <a name="properties"></a>属性

| 属性      | 类型      | 说明    |
|:--------------|:----------|:---------------|
|式         |Boolean    | `true` 如果该属性应用作对象的定位标记。 定位属性必须具有标识对象的唯一值，并且必须是不可变的。 默认值为 `false`。 必须将对象的一个属性（且只有一个）指定为支持同步的定位点。 |
|caseExact      |Boolean    |`true` 如果应将此属性的值视为区分大小写。 此设置影响同步引擎检测属性更改的方式。|
|flowNullValues |Boolean    |若要允许属性的值为 null，则为 "true"。|
|metadata       |[metadataEntry](../resources/synchronization-metadataentry.md) 集合   |其他扩展属性。 除非明确提到，否则不应更改元数据值。|
|多    |Boolean    |`true` 如果属性可以有多个值。 默认值为 `false`。|
|mutability     |String     |属性的 mutability。 可能的值为：  `ReadWrite` 、 `ReadOnly` 、 `Immutable` 、 `WriteOnly` 。 默认值为 `ReadWrite`。|
|名称           |String     |属性的名称。 在对象定义中必须是唯一的。 不可为空。|
|必需       |Boolean    |`true` if 属性是必需的。 如果缺少任何必需的属性，则不能创建对象。 如果在同步过程中，所需的属性没有任何值，则将使用默认值。 如果默认值未设置，则同步将记录一个错误。|
|referencedObjects|[referencedObject](../resources/synchronization-referencedobject.md) 集合 |对于 `reference` "类型" 的属性，列出被引用的对象 (例如， `manager` 属性将 `User` 作为引用的对象列出) 。|
|type           |String     |属性值类型。 可取值为：`String`、`Integer`、`Reference`、`Binary` 或 `Boolean`。 默认值为 `String`。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.attributeDefinition"
}-->

```json
{
  "anchor": true,
  "caseExact": true,
  "defaultValue": "String",
  "flowNullValues": true,
  "metadata": [{"@odata.type": "microsoft.graph.metadataEntry"}],
  "multivalued": true,
  "mutability": "String",
  "name": "String",
  "referencedObjects": [{"@odata.type": "microsoft.graph.referencedObject"}],
  "required": true,
  "type": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "attributeDefinition resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


