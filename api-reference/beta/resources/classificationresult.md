---
title: classificationResult 资源类型
description: 表示分类请求的结果。
localization_priority: Normal
author: tommoser
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: 903284f99933c131a24474ac6f024a2c4c2550f1
ms.sourcegitcommit: 7ceec757fd82ef3fd80aa3089ef46d3807aa3aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48405580"
---
# <a name="classificationresult-resource-type"></a>classificationResult 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示来自 Microsoft 分类引擎的分类操作的结果。 来自 Azure 信息保护、Office 和其他 Microsoft 服务的数据分类结果可能会返回一 [组定义完善的分类类型](/office365/securitycompliance/what-the-sensitive-information-types-look-for)。 可以向 [evaluateClassificationResults](../api/informationprotectionlabel-evaluateclassificationresults.md) API 提供这些类型，以将敏感信息解析为 Microsoft 信息保护标签。 

## <a name="properties"></a>属性

| 属性        | 类型  | 说明                                                            |
| :-------------- | :---- | :--------------------------------------------------------------------- |
| confidenceLevel | Int32 | 结果的置信度（0到100）。                         |
| count           | Int32 | 输入中特定信息类型的实例数。 |
| sensitiveTypeId | GUID  | 发现的敏感信息类型的 GUID。                 |

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.classificationResult",
  "baseType": null
}-->

```json
{
  "confidenceLevel": 1024,
  "count": 1024,
  "sensitiveTypeId": "Guid"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "classificationResult resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->