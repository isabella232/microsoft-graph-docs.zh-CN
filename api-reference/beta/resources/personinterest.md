---
title: personInterest 资源类型
description: personInterest 资源类型
localization_priority: Normal
author: kevinbellinger
ms.prod: people
doc_type: resourcePageType
ms.openlocfilehash: 7071f089c7dbc9ff309dfc1d45628ef24c367567
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47997958"
---
# <a name="personinterest-resource-type"></a>personInterest 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

提供有关用户在各种服务中与其自身关联的兴趣的详细信息。

继承自 [itemFacet](itemfacet.md)。

## <a name="methods"></a>方法

| 方法                                                    | 返回类型                         | 说明                                                           |
|:----------------------------------------------------------|:------------------------------------|:----------------------------------------------------------------------|
|[列出兴趣](../api/profile-list-interests.md)|[personInterest](../resources/personinterest.md) 集合|从 "兴趣" 导航属性中获取 personInterest 资源。|
|[创建 personInterest](../api/profile-post-interests.md)|[personInterest](../resources/personinterest.md)|创建新的 personInterest 对象。|
|[获取 personInterest](../api/personinterest-get.md)|[personInterest](../resources/personinterest.md)|读取 [personInterest](../resources/personinterest.md) 对象的属性和关系。|
|[更新 personInterest](../api/personinterest-update.md)|[personInterest](../resources/personinterest.md)|更新 [personInterest](../resources/personinterest.md) 对象的属性。|
|[删除 personInterest](../api/personinterest-delete.md)|无|删除一个 [personInterest](../resources/personinterest.md) 对象。|

## <a name="properties"></a>属性

|属性|类型|说明|
|:---|:---|:---|
|allowedAudiences|String|能够查看实体中包含的值的访问群体。 继承自 [itemFacet](../resources/itemfacet.md)。 可取值为：`me`、`family`、`contacts`、`groupMembers`、`organization`、`federatedOrganizations`、`everyone`、`unknownFutureValue`。|
|类别|String collection|包含用户与兴趣相关联的类别 (例如，个人 recipies) 。 |
|collaborationTags|String collection|包含用户与兴趣相关的体验方案标记。 集合中允许的值为： `askMeAbout` 、 `ableToMentor` 、 `wantsToLearn` 、 `wantsToImprove` 。|
|createdBy|[identitySet](../resources/identityset.md)|提供创建实体的用户和/或应用程序的标识符。 继承自 [itemFacet](../resources/itemfacet.md)。|
|createdDateTime|DateTimeOffset|为创建实体时提供 dateTimeOffset。 继承自 [itemFacet](../resources/itemfacet.md)。|
|description|String|包含对利息的说明。|
|displayName|String|包含利息的友好名称。  |
|id|String|用于单独寻址实体的标识符。 继承自 [entity](../resources/entity.md)|
|推导|[inferenceData](../resources/inferencedata.md)|如果实体是由创建或修改应用程序推断的，则包含推理详细信息。 继承自 [itemFacet](../resources/itemfacet.md)。|
|lastModifiedBy|[identitySet](../resources/identityset.md)|提供上次修改实体的用户和/或应用程序的标识符。 继承自 [itemFacet](../resources/itemfacet.md)。|
|lastModifiedDateTime|DateTimeOffset|为创建实体时提供 dateTimeOffset。 继承自 [itemFacet](../resources/itemfacet.md)。|
|source|[personDataSource](../resources/persondatasource.md)|值的来源，如果从另一个服务同步。 继承自 [itemFacet](../resources/itemfacet.md)。|
|webUrl|String|包含指向有关该兴趣的网页或资源的链接。 |

## <a name="relationships"></a>关系

无。

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.personInterest",
  "baseType": ""
}-->

```json
{
  "@odata.type": "#microsoft.graph.personInterest",
  "id": "String (identifier)",
  "allowedAudiences": "String",
  "inference": {
    "@odata.type": "microsoft.graph.inferenceData"
  },
  "createdDateTime": "String (timestamp)",
  "createdBy": {
    "@odata.type": "microsoft.graph.identitySet"
  },
  "lastModifiedDateTime": "String (timestamp)",
  "lastModifiedBy": {
    "@odata.type": "microsoft.graph.identitySet"
  },
  "source": {
    "@odata.type": "microsoft.graph.personDataSource"
  },
  "categories": [
    "String"
  ],
  "description": "String",
  "displayName": "String",
  "webUrl": "String",
  "collaborationTags": [
    "String"
  ]
}
```


