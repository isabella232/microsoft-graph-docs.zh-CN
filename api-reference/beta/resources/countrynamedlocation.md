---
title: countryNamedLocation 资源类型
description: 表示由国家和地区定义的、名为 "位置" 的 Azure Active Directory。 "已命名位置" 是自定义规则，用于定义随后可在条件访问策略中使用的网络位置。
localization_priority: Normal
author: dkershaw10
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: 8c4807abc04cb980ec452590b9643f2b07d0ce67
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48016700"
---
# <a name="countrynamedlocation-resource-type"></a>countryNamedLocation 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示由国家和地区定义的、名为 "位置" 的 Azure Active Directory。 "已命名位置" 是自定义规则，用于定义随后可在条件访问策略中使用的网络位置。

继承自 [namedLocation](../resources/namedLocation.md)

## <a name="methods"></a>方法

| 方法       | 返回类型 | 说明 |
|:-------------|:------------|:------------|
| [列出 countryNamedLocations](../api/conditionalaccessroot-list-namedlocations.md) | [countryNamedLocation](countryNamedLocation.md) 集合 | 获取组织中的所有 **countryNamedLocation** 对象。 |
| [创建 countryNamedLocation](../api/conditionalaccessroot-post-namedlocations.md) | [countryNamedLocation](countryNamedLocation.md) | 创建新的 **countryNamedLocation** 对象。 |
| [获取 countryNamedLocation](../api/countrynamedlocation-get.md) | [countryNamedLocation](countrynamedlocation.md) | 读取 **countryNamedLocation** 对象的属性和关系。 |
| [更新 countryNamedLocation](../api/countrynamedlocation-update.md) | [countryNamedLocation](countrynamedlocation.md) | 更新 **countryNamedLocation** 对象。 |
| [删除 countryNamedLocation](../api/countrynamedlocation-delete.md) | 无 | 删除 **countryNamedLocation** 对象。 |

## <a name="properties"></a>属性

| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|countriesAndRegions|String 集合|由 ISO 3166-2 指定的两个字母格式的国家/地区和/或地区列表。|
|createdDateTime|DateTimeOffset|时间戳类型表示使用 ISO 8601 格式的位置的创建日期和时间，并且始终采用 UTC 时间。 例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`。 只读。 继承自 [namedLocation](../resources/namedLocation.md)。|
|displayName|String|位置的人可读名称。 继承自 [namedLocation](../resources/namedLocation.md)。|
|id|String|NamedLocation 对象的标识符。 只读。 继承自 [namedLocation](../resources/namedLocation.md)。|
|includeUnknownCountriesAndRegions|Boolean|如此如果未映射到国家或地区的 IP 地址应包含在指定的位置。|
|modifiedDateTime|DateTimeOffset|时间戳类型表示上次修改的位置使用 ISO 8601 格式的日期和时间，并且始终采用 UTC 时间。 例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`。 只读。 继承自 [namedLocation](../resources/namedLocation.md)。|

## <a name="relationships"></a>关系

无。

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.countryNamedLocation",
  "baseType": ""
}-->

```json
{
  "countriesAndRegions": ["String"],
  "createdDateTime": "String (timestamp)",
  "displayName": "String",
  "id": "String (identifier)",
  "includeUnknownCountriesAndRegions": true,
  "modifiedDateTime": "String (timestamp)"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "countryNamedLocation resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


