---
title: win32LobAppMsiInformation 资源类型
description: 包含 Win32 应用程序的 MSI 应用程序属性。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: a812789a8231731b171edea8e15f7f540266cbde
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48080078"
---
# <a name="win32lobappmsiinformation-resource-type"></a>win32LobAppMsiInformation 资源类型

命名空间：microsoft.graph

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的[活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

包含 Win32 应用程序的 MSI 应用程序属性。

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|productCode|String|MSI 产品代码。|
|productVersion|String|MSI 产品版本。|
|upgradeCode|String|MSI 升级代码。|
|requiresReboot|Boolean|MSI 应用是否需要计算机重新启动以完成安装。|
|packageType|[win32LobAppMsiPackageType](../resources/intune-apps-win32lobappmsipackagetype.md)|MSI 包类型。 可取值为：`perMachine`、`perUser`、`dualPurpose`。|
|productName|String|MSI 产品名称。|
|发布者|String|MSI 发布者。|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.win32LobAppMsiInformation"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.win32LobAppMsiInformation",
  "productCode": "String",
  "productVersion": "String",
  "upgradeCode": "String",
  "requiresReboot": true,
  "packageType": "String",
  "productName": "String",
  "publisher": "String"
}
```





