---
title: deviceManagementScriptAssignment 资源类型
description: 包含用于将设备管理脚本分配给组的属性。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: 072d11542b186459ca57dfa9fc575e05f8189766
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49299203"
---
# <a name="devicemanagementscriptassignment-resource-type"></a>deviceManagementScriptAssignment 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

包含用于将设备管理脚本分配给组的属性。

## <a name="methods"></a>Methods
|方法|返回类型|Description|
|:---|:---|:---|
|[列出 deviceManagementScriptAssignments](../api/intune-devices-devicemanagementscriptassignment-list.md)|[deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md) 集合|列出 [deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md) 对象的属性和关系。|
|[获取 deviceManagementScriptAssignment](../api/intune-devices-devicemanagementscriptassignment-get.md)|[deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md)|读取 [deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md) 对象的属性和关系。|
|[创建 deviceManagementScriptAssignment](../api/intune-devices-devicemanagementscriptassignment-create.md)|[deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md)|创建新的 [deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md) 对象。|
|[删除 deviceManagementScriptAssignment](../api/intune-devices-devicemanagementscriptassignment-delete.md)|无|删除 [deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md)。|
|[更新 deviceManagementScriptAssignment](../api/intune-devices-devicemanagementscriptassignment-update.md)|[deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md)|更新 [deviceManagementScriptAssignment](../resources/intune-devices-devicemanagementscriptassignment.md) 对象的属性。|

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|id|字符串|Device management script group 分配实体的键。 此属性是只读的。|
|target|[deviceAndAppManagementAssignmentTarget](../resources/intune-shared-deviceandappmanagementassignmenttarget.md)|要作为脚本目标的 Azure Active Directory 组的 Id。|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.deviceManagementScriptAssignment"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceManagementScriptAssignment",
  "id": "String (identifier)",
  "target": {
    "@odata.type": "microsoft.graph.allDevicesAssignmentTarget",
    "deviceAndAppManagementAssignmentFilterId": "String",
    "deviceAndAppManagementAssignmentFilterType": "String"
  }
}
```




