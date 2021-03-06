---
title: bookingCurrency 资源类型
description: " > **重要说明：** Microsoft Graph 中 /beta 版本下的 API 是预览版，可能会发生变化。 不支持在生产应用程序中使用这些 API。"
localization_priority: Normal
author: arvindmicrosoft
ms.prod: bookings
doc_type: resourcePageType
ms.openlocfilehash: f4b5cc6a8fdb36c2e4543302ac32846a1b3c4388
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48071792"
---
# <a name="bookingcurrency-resource-type"></a>bookingCurrency 资源类型

命名空间：microsoft.graph

 [!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]
 
表示 [bookingBusiness](bookingbusiness.md)支持的货币货币。


## <a name="methods"></a>方法

| 方法           | 返回类型    |说明|
|:---------------|:--------|:----------|
|[列出 bookingCurrencies](../api/bookingcurrency-list.md) | [bookingCurrency](bookingcurrency.md) 集合 |获取可用于 Microsoft 预订业务的 **bookingCurrency** 对象的列表。|
|[获取 bookingCurrency](../api/bookingcurrency-get.md) | [bookingCurrency](bookingcurrency.md) |获取 **bookingCurrency** 对象的属性。|


## <a name="properties"></a>属性
| 属性     | 类型   |说明|
|:---------------|:--------|:----------|
|id|String| 基于 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html)的3个字符的货币代码。 例如，美元的货币代码是 USD，而澳大利亚美元是 AUD。 只读。|
|符号|String| 货币符号。 例如，美元的货币符号和澳大利亚美元为美元。  |

## <a name="relationships"></a>关系
无


## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.bookingCurrency"
}-->

```json
{
  "id": "String (identifier)",
  "symbol": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "bookingCurrency resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


