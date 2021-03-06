---
title: authenticationMethodConfigurations
description: authenticationMethodConfigurations 对象。
author: mmcla
localization_priority: Normal
ms.prod: microsoft-identity-platform
doc_type: apiPageType
ms.openlocfilehash: 856db11063c3f766f07ff725fe172270449d272d
ms.sourcegitcommit: cfadc605014265e02b913bc77382025b0d156285
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418281"
---
# <a name="authenticationmethodconfiguration-resource-type"></a>authenticationMethodConfiguration 资源类型
命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示身份验证方法策略。

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|id|字符串|策略名称。|
|state|authenticationMethodState|策略的状态。 可取值为：`enabled`、`disabled`。|

## <a name="relationships"></a>关系
无。

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.authenticationMethodConfiguration",
  "baseType": "",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.authenticationMethodConfiguration",
  "id": "String (identifier)",
  "state": "String"
}
```
