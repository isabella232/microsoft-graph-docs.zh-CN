---
title: plannerRecentPlanReferenceCollection 资源类型
description: '**PlannerRecentPlanReferenceCollection**资源表示对用户最近查看的计划的引用集合。 此资源是打开的类型，并且是 plannerUser 对象的一部分。 属性名称是对应计划的 ID。 属性-值对中的值是 plannerRecentPlanReference 对象。'
localization_priority: Normal
author: TarkanSevilmis
ms.prod: planner
doc_type: resourcePageType
ms.openlocfilehash: 529552be4497729824ddfb9fa9e84ea82e8ccd0d
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48064003"
---
# <a name="plannerrecentplanreferencecollection-resource-type"></a>plannerRecentPlanReferenceCollection 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**PlannerRecentPlanReferenceCollection**资源表示对用户最近查看的计划的引用集合。 此资源是打开的类型，并且是 [plannerUser](planneruser.md) 对象的一部分。 属性名称是对应计划的 ID。 属性-值对中的值是 [plannerRecentPlanReference](plannerrecentplanreference.md) 对象。
如果将新的引用添加到此集合中，则当集合的大小超过预先确定的最大值时，将自动删除最旧的项。


## <a name="properties"></a>属性
您可以定义此开放类型的属性。 属性名称是 `id` [plannerPlan](plannerplan.md) 资源的值，它们的值必须是 [plannerRecentPlanReference](plannerrecentplanreference.md) 对象。 若要删除收藏夹列表中的项，请将该属性的值设置为 `null` 。


## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.plannerRecentPlanReferenceCollection"
}-->

```json
{
  "7oTB5aMIAE2rVo-1N-L7RmQAGX2q": {
    "@odata.type": "microsoft.graph.plannerRecentPlanReference",
    "lastAccessedDateTime": "2017-12-02T22:49:46.155Z",
    "planTitle": "Purchase Workflow"
  },
  "iKNMHkk3vEWpSF7F7iZWIGQAAMMw": {
    "@odata.type": "microsoft.graph.plannerRecentPlanReference",
    "lastAccessedDateTime": "2017-12-03T21:59:28.975Z",
    "planTitle": "New Year's Office Party"
  }
}
```



<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "plannerRecentPlanReferenceCollection resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


