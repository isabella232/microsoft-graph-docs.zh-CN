---
title: deviceCategory 资源类型
description: 然后可将这些类别应用于 Intune Azure 控制台中的设备，或在用户注册设备时供他们选择。 可以根据设备类别筛选报告并创建动态 Azure Active Directory 设备组。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: 14ff0efe2532fd808e94c27c68777c4935212b01
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49306896"
---
# <a name="devicecategory-resource-type"></a>deviceCategory 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

设备类别提供了一种组织设备的方法。 使用设备类别，公司管理员可以定义对其公司有意义的独特类别。 然后可将这些类别应用于 Intune Azure 控制台中的设备，或在用户注册设备时供他们选择。 可以根据设备类别筛选报告并创建动态 Azure Active Directory 设备组。

## <a name="methods"></a>Methods
|方法|返回类型|Description|
|:---|:---|:---|
|[List deviceCategories](../api/intune-shared-devicecategory-list.md)|[deviceCategory](../resources/intune-shared-devicecategory.md) 集合|列出 [deviceCategory](../resources/intune-shared-devicecategory.md) 对象的属性和关系。|
|[Get deviceCategory](../api/intune-shared-devicecategory-get.md)|[deviceCategory](../resources/intune-shared-devicecategory.md)|读取 [deviceCategory](../resources/intune-shared-devicecategory.md) 对象的属性和关系。|
|[Create deviceCategory](../api/intune-shared-devicecategory-create.md)|[deviceCategory](../resources/intune-shared-devicecategory.md)|创建新的 [deviceCategory](../resources/intune-shared-devicecategory.md) 对象。|
|[Delete deviceCategory](../api/intune-shared-devicecategory-delete.md)|无|删除 [deviceCategory](../resources/intune-shared-devicecategory.md)。|
|[Update deviceCategory](../api/intune-shared-devicecategory-update.md)|[deviceCategory](../resources/intune-shared-devicecategory.md)|更新 [deviceCategory](../resources/intune-shared-devicecategory.md) 对象的属性。|

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|id|字符串|设备类别的唯一标识符。 只读。|
|**载入**|
|displayName|字符串|设备类别的显示名称。|
|description|字符串|设备类别的说明（可选）。|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.deviceCategory"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceCategory",
  "id": "String (identifier)",
  "displayName": "String",
  "description": "String"
}
```




