---
title: deviceManagementTroubleshootingErrorResource 资源类型
description: 表示指向疑难解答信息的链接的对象，则该链接可能指向 Azure 门户或 Microsoft doc。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: 0dd4db93e49b274b9992bd91612c6a384daecdef
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49255299"
---
# <a name="devicemanagementtroubleshootingerrorresource-resource-type"></a>deviceManagementTroubleshootingErrorResource 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

表示指向疑难解答信息的链接的对象，则该链接可能指向 Azure 门户或 Microsoft doc。

## <a name="properties"></a>属性
|属性|类型|描述|
|:---|:---|:---|
|text|String|尚未记录|
|link|String|指向 web 资源的链接。 可以包含以下任何格式化程序： {{UPN}}、{{DeviceGUID}}、{{UserGUID}}|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.deviceManagementTroubleshootingErrorResource"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceManagementTroubleshootingErrorResource",
  "text": "String",
  "link": "String"
}
```




