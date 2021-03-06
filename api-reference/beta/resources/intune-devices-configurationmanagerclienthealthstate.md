---
title: configurationManagerClientHealthState 资源类型
description: 配置管理器客户端运行状况
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: 4794efda5df6bcb4904afe297704c86379aaa8ed
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49231029"
---
# <a name="configurationmanagerclienthealthstate-resource-type"></a>configurationManagerClientHealthState 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

配置管理器客户端运行状况

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|state|[configurationManagerClientState](../resources/intune-devices-configurationmanagerclientstate.md)|当前配置管理器客户端状态。 可取值为：`unknown`、`installed`、`healthy`、`installFailed`、`updateFailed`、`communicationError`。|
|errorCode|Int32|失败状态的错误代码。|
|lastSyncDateTime|DateTimeOffset|与 configuration manager 管理点进行上一次同步的日期/时间。|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.configurationManagerClientHealthState"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.configurationManagerClientHealthState",
  "state": "String",
  "errorCode": 1024,
  "lastSyncDateTime": "String (timestamp)"
}
```




