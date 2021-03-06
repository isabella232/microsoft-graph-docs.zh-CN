---
title: secureScore 资源类型
description: 表示租户和控制级别上的每日记分数据的租户安全分数。
localization_priority: Normal
author: preetikr
ms.prod: ''
doc_type: resourcePageType
ms.openlocfilehash: e4f798ae64b881c95ed4330901c0a34ba4073f0e
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47984094"
---
# <a name="securescore-resource-type"></a>secureScore 资源类型

命名空间：microsoft.graph

表示租户和控制级别上的每日记分数据的租户安全分数。 默认情况下，将保留90天的数据。 此数据按 **createdDateTime**进行排序，从最新到最早。 这将允许您使用 $top = n 对响应进行分页，其中 n = 要检索的数据的天数。 


## <a name="methods"></a>方法

| 方法   | 返回类型|说明|
|:---------------|:--------|:----------|
|[列出 secureScores](../api/security-list-securescores.md) | [secureScores](securescore.md) 集合 |获取 secureScore 对象集合。|
|[获取 secureScore](../api/securescore-get.md) | [secureScore](securescore.md) |读取 secureScore 对象的属性和元数据。 | 



## <a name="properties"></a>属性

|属性 |类型 |说明 |
|:--|:--|:--|
|id |String|提供程序生成的 GUID/唯一标识符。 只读。 必需。|
|   azureTenantId   |   字符串  |   租户 ID 的 GUID 字符串。  |
|   activeUserCount |   Int32   |   给定租户的活动用户计数。  |
|   createdDateTime |   DateTimeOffset  |   创建实体的日期。  |
|   currentScore    |   双精度  |   租户当前在指定日期的得分。    |
|   enabledServices |   String collection   |   Microsoft 为租户提供的服务 (例如，Exchange online、Skype、Sharepoint) 。   |
|   licensedUserCount   |   Int32   |   给定租户的许可用户计数。    |
|   maxScore |  双精度  |   指定日期上可能的租户最大分数。    |
|   averageComparativeScores |  [averageComparativeScore](averagecomparativescore.md) 集合    |不同作用域的平均分数 (例如，行业平均值、座位) 和控制类别的平均 (标识、数据、设备、应用程序、基础结构) 在范围内。 |
|   controlScores | [controlScore](controlscore.md) 集合  |   包含一组控件的租户分数。   |
|vendorInformation |[securityVendorInformation](securityvendorinformation.md)|包含有关安全产品/服务供应商、提供商和 subprovider 的详细信息的复杂类型 (例如，供应商 = Microsoft;provider = SecureScore) 。 必需。|


## <a name="relationships"></a>关系

无。

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.secureScore"
}-->

```json
{
"id": "String (identifier)",
"azureTenantId": "String",
"activeUserCount": "Int32",
"createdDateTime": "String (timestamp)",
"currentScore": "Double",
"enabledServices": ["String"],
"licensedUserCount": "Int32",
"maxScore": "Double",
"averageComparativeScores": [{"@odata.type": "microsoft.graph.averageComparativeScore"}],
"controlScores": [{"@odata.type": "microsoft.graph.controlScore"}],
"vendorInformation": {"@odata.type": "microsoft.graph.securityVendorInformation"},
}

```


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "secureScore resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

