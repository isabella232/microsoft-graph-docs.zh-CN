---
title: networkIPv4ConfigurationManagementCondition 资源类型
description: 可能会定义在设备检测到特定 IP 网络设置时触发的基于配置的 IPv4 管理条件。 只有在网络连接处于活动状态时，才会将 IP 配置管理条件视为 TRUE。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: b165d80dee7deedc7a7039b00e2fecfe6e88ab21
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49299056"
---
# <a name="networkipv4configurationmanagementcondition-resource-type"></a>networkIPv4ConfigurationManagementCondition 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

可能会定义在设备检测到特定 IP 网络设置时触发的基于配置的 IPv4 管理条件。 只有在网络连接处于活动状态时，才会将 IP 配置管理条件视为 TRUE。


继承自 [networkManagementCondition](../resources/intune-fencing-networkmanagementcondition.md)

## <a name="methods"></a>Methods
|方法|返回类型|Description|
|:---|:---|:---|
|[列出 networkIPv4ConfigurationManagementConditions](../api/intune-fencing-networkipv4configurationmanagementcondition-list.md)|[networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md) 集合|列出 [networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md) 对象的属性和关系。|
|[获取 networkIPv4ConfigurationManagementCondition](../api/intune-fencing-networkipv4configurationmanagementcondition-get.md)|[networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md)|读取 [networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md) 对象的属性和关系。|
|[创建 networkIPv4ConfigurationManagementCondition](../api/intune-fencing-networkipv4configurationmanagementcondition-create.md)|[networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md)|创建新的 [networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md) 对象。|
|[删除 networkIPv4ConfigurationManagementCondition](../api/intune-fencing-networkipv4configurationmanagementcondition-delete.md)|无|删除 [networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md)。|
|[更新 networkIPv4ConfigurationManagementCondition](../api/intune-fencing-networkipv4configurationmanagementcondition-update.md)|[networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md)|更新 [networkIPv4ConfigurationManagementCondition](../resources/intune-fencing-networkipv4configurationmanagementcondition.md) 对象的属性。|

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|id|字符串|管理条件的唯一标识符。 创建时分配的系统生成值。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|
|uniqueName|字符串|管理条件的唯一名称。 在管理条件表达式中使用。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|
|displayName|字符串|管理条件的管理员定义名称。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|
|description|字符串|管理条件的管理员定义的说明。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|
|createdDateTime|DateTimeOffset|管理条件的创建时间。 生成的服务端。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|
|modifiedDateTime|DateTimeOffset|上次修改管理条件的时间。 更新了服务端。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|
|eTag|String|管理条件的 ETag。 更新了服务端。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|
|applicablePlatforms|[devicePlatformType](../resources/intune-shared-deviceplatformtype.md) 集合|适用于此管理条件的平台。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|
|ipV4Prefix|字符串|要连接到的 IPv4 子网。 例如，10.0.0.0/8|
|ipV4Gateway|字符串|IPv4 网关地址。 例如10.0.0。0|
|ipV4DHCPServer|字符串|适配器的 DHCP 服务器的 IPv4 地址。|
|ipV4DNSServerList|String 集合|为适配器配置的 IPv4 DNS 服务器。|
|dnsSuffixList|String 集合|当前网络的有效 DNS 后缀。 例如 seattle.contoso.com|

## <a name="relationships"></a>关系
|关系|类型|Description|
|:---|:---|:---|
|managementConditionStatements|[managementConditionStatement](../resources/intune-fencing-managementconditionstatement.md) 集合|与管理条件相关联的管理条件语句。 继承自 [managementCondition](../resources/intune-fencing-managementcondition.md)|

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.networkIPv4ConfigurationManagementCondition"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.networkIPv4ConfigurationManagementCondition",
  "id": "String (identifier)",
  "uniqueName": "String",
  "displayName": "String",
  "description": "String",
  "createdDateTime": "String (timestamp)",
  "modifiedDateTime": "String (timestamp)",
  "eTag": "String",
  "applicablePlatforms": [
    "String"
  ],
  "ipV4Prefix": "String",
  "ipV4Gateway": "String",
  "ipV4DHCPServer": "String",
  "ipV4DNSServerList": [
    "String"
  ],
  "dnsSuffixList": [
    "String"
  ]
}
```




