---
title: deliveryOptimizationBandwidthPercentage 资源类型
description: 以百分比形式指定的带宽限制。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: 85dc858431b15a142a42afc74b1b7c1ba76a4667
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49199607"
---
# <a name="deliveryoptimizationbandwidthpercentage-resource-type"></a>deliveryOptimizationBandwidthPercentage 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

以百分比形式指定的带宽限制。


继承自 [deliveryOptimizationBandwidth](../resources/intune-deviceconfig-deliveryoptimizationbandwidth.md)

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|maximumBackgroundBandwidthPercentage|Int32|指定传递优化在所有并发下载活动中使用的最大后台下载带宽，以 (0-100) 的可用下载带宽的百分比表示。 有效值为 0 至 100
默认值 0 (零) 意味着传递优化将动态调整，以使用可用带宽进行后台下载。 有效值为 0 至 100|
|maximumForegroundBandwidthPercentage|Int32|指定传递优化在所有并发下载活动中使用的最大前台下载带宽，以可用下载带宽的百分比 (0-100) 为依据。 有效值为 0 至 100
默认值 0 (零) 意味着传递优化将动态调整，以使用可用带宽进行前台下载。 有效值为 0 至 100|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.deliveryOptimizationBandwidthPercentage"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deliveryOptimizationBandwidthPercentage",
  "maximumBackgroundBandwidthPercentage": 1024,
  "maximumForegroundBandwidthPercentage": 1024
}
```




