---
title: userExperienceAnalyticsAppHealthOSVersionPerformance 资源类型
description: User experience analytics device OS version performance entity 包含 OS 版本性能详细信息。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: 404d40b0924b78eec5a0690fe4986421f84c05f2
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49208476"
---
# <a name="userexperienceanalyticsapphealthosversionperformance-resource-type"></a>userExperienceAnalyticsAppHealthOSVersionPerformance 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

User experience analytics device OS version performance entity 包含 OS 版本性能详细信息。

## <a name="methods"></a>方法
|方法|返回类型|说明|
|:---|:---|:---|
|[列出 userExperienceAnalyticsAppHealthOSVersionPerformances](../api/intune-devices-userexperienceanalyticsapphealthosversionperformance-list.md)|[userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md) 集合|列出 [userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md) 对象的属性和关系。|
|[获取 userExperienceAnalyticsAppHealthOSVersionPerformance](../api/intune-devices-userexperienceanalyticsapphealthosversionperformance-get.md)|[userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md)|读取 [userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md) 对象的属性和关系。|
|[创建 userExperienceAnalyticsAppHealthOSVersionPerformance](../api/intune-devices-userexperienceanalyticsapphealthosversionperformance-create.md)|[userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md)|创建新的 [userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md) 对象。|
|[删除 userExperienceAnalyticsAppHealthOSVersionPerformance](../api/intune-devices-userexperienceanalyticsapphealthosversionperformance-delete.md)|无|删除 [userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md)。|
|[更新 userExperienceAnalyticsAppHealthOSVersionPerformance](../api/intune-devices-userexperienceanalyticsapphealthosversionperformance-update.md)|[userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md)|更新 [userExperienceAnalyticsAppHealthOSVersionPerformance](../resources/intune-devices-userexperienceanalyticsapphealthosversionperformance.md) 对象的属性。|

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|id|String|User experience analytics OS 版本性能对象的唯一标识符。|
|osVersion|String|设备上安装的 OS 版本。|
|osBuildNumber|String|安装在设备上的操作系统内部版本号。|
|activeDeviceCount|Int32|OS 版本的活动设备数。 有效值-2147483648 到2147483647|
|meanTimeToFailureInMinutes|Int32|OS 版本失败的平均时间，以分钟为单位。 有效值-2147483648 到2147483647|
|osVersionAppHealthScore|双精度|操作系统版本的应用运行状况分数。 有效值-1.79769313486232 E + 308 到 1.79769313486232 E + 308|
|osVersionAppHealthStatus|String|OS 版本的总体应用程序运行状况状态。|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.userExperienceAnalyticsAppHealthOSVersionPerformance"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.userExperienceAnalyticsAppHealthOSVersionPerformance",
  "id": "String (identifier)",
  "osVersion": "String",
  "osBuildNumber": "String",
  "activeDeviceCount": 1024,
  "meanTimeToFailureInMinutes": 1024,
  "osVersionAppHealthScore": "4.2",
  "osVersionAppHealthStatus": "String"
}
```




