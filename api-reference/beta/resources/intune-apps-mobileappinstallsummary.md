---
title: mobileAppInstallSummary 资源类型
description: 包含移动应用程序的安装摘要的属性。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: dbab510c7f19defa3fd3a26c41bd86ed5866f5ff
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49231899"
---
# <a name="mobileappinstallsummary-resource-type"></a>mobileAppInstallSummary 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

包含移动应用程序的安装摘要的属性。

## <a name="methods"></a>方法
|方法|返回类型|说明|
|:---|:---|:---|
|[获取 mobileAppInstallSummary](../api/intune-apps-mobileappinstallsummary-get.md)|[mobileAppInstallSummary](../resources/intune-apps-mobileappinstallsummary.md)|读取 [mobileAppInstallSummary](../resources/intune-apps-mobileappinstallsummary.md) 对象的属性和关系。|
|[更新 mobileAppInstallSummary](../api/intune-apps-mobileappinstallsummary-update.md)|[mobileAppInstallSummary](../resources/intune-apps-mobileappinstallsummary.md)|更新 [mobileAppInstallSummary](../resources/intune-apps-mobileappinstallsummary.md) 对象的属性。|

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|id|String|实体的键。|
|installedDeviceCount|Int32|已成功安装此应用的设备数量。|
|failedDeviceCount|Int32|安装此应用失败的设备数量。|
|notApplicableDeviceCount|Int32|不适用于此应用程序的设备数量。|
|notInstalledDeviceCount|Int32|未安装此应用的设备数量。|
|pendingInstallDeviceCount|Int32|已通知安装此应用程序的设备数。|
|installedUserCount|Int32|其设备已成功安装此应用程序的用户数。|
|failedUserCount|Int32|具有1个或多个无法安装此应用程序的设备的用户数。|
|notApplicableUserCount|Int32|其设备全部不适用于此应用的用户数。|
|notInstalledUserCount|Int32|具有1个或多个未安装此应用程序的设备的用户数。|
|pendingInstallUserCount|Int32|具有1个或多个设备且已收到安装此应用程序并有0个设备出现故障的用户数量。|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.mobileAppInstallSummary"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.mobileAppInstallSummary",
  "id": "String (identifier)",
  "installedDeviceCount": 1024,
  "failedDeviceCount": 1024,
  "notApplicableDeviceCount": 1024,
  "notInstalledDeviceCount": 1024,
  "pendingInstallDeviceCount": 1024,
  "installedUserCount": 1024,
  "failedUserCount": 1024,
  "notApplicableUserCount": 1024,
  "notInstalledUserCount": 1024,
  "pendingInstallUserCount": 1024
}
```




