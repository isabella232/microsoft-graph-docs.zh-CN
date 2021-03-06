---
title: externalDomainFederation 资源类型
description: ExternalDomainFederation 类型将具有配置的标识提供程序的非租户域标识为连接的组织的标识源。
localization_priority: Normal
author: markwahl-msft
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: d81255a3687bf3d6aafe9369f901b209f5827b77
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48026913"
---
# <a name="externaldomainfederation-resource-type"></a>externalDomainFederation 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

在 [connectedOrganization](connectedOrganization.md)的标识源中使用。 `@odata.type`该值 `#microsoft.graph.externalDomainFederation` 指示此类型将具有已配置标识提供程序的域标识为连接的组织的标识源。

## <a name="properties"></a>属性

| 属性                     | 类型                      | 说明 |
| :--------------------------- | :------------------------ | :---------- |
| displayName |String | 标识源的名称，通常也是域名。 只读。 |
| domainName |String | 域名称。 只读。 |
| issuerUri |String | 传入联合身份验证的 issuerURI。 只读。 |

## <a name="relationships"></a>关系

无。

## <a name="json-representation"></a>JSON 表示形式

以下是类型的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.externalDomainFederation",
  "baseType": "microsoft.graph.identitySource"
}-->

```json
{
  "domainName": "String",
  "displayName": "String",
  "issuerUri": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "externalDomainFederation resource type",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


