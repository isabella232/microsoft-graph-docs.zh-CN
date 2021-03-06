---
title: provisioningObjectSummary 资源类型
description: 表示由 Azure AD 预配服务及其关联的属性执行的操作。
localization_priority: Normal
author: ArvindHarinder1
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: 8bf8813b63d1d25d09c8ee9a8ff4bb5099728b77
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47993117"
---
# <a name="provisioningobjectsummary-resource-type"></a>provisioningObjectSummary 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示由 Azure AD 预配服务及其关联的属性执行的操作。 

## <a name="methods"></a>方法

| 方法  | 返回类型 | 说明 |
|:-------------|:------------|:------------|
| [列出 provisioningObjectSummary](../api/provisioningobjectsummary-list.md) | [provisioningObjectSummary](provisioningobjectsummary.md) | 获取租户中发生的所有设置事件的列表。 |


## <a name="properties"></a>属性

| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|action|String|指示活动名称或操作名称 (例如，创建用户，将 member 添加到 group) 中。 有关已记录活动的列表，请参阅 Azure AD 活动列表。|
|activityDateTime|DateTimeOffset|时间戳类型表示使用 ISO 8601 格式的日期和时间信息，并且始终处于 UTC 时间。例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`|
|changeId|String|此周期中的此更改的唯一 ID。|
|cycleId|String|每个作业迭代的唯一 ID。|
|durationInMilliseconds|Int32|指示此设置操作完成所花的时间。 以毫秒为单位。|
|id|String| 指示活动的唯一 ID。 这是只读的 GUID。|
|initiatedBy|[initiator](initiator.md)|启动此预配的参与者的详细信息。|
|jobId|String|整个设置作业的唯一 ID。|
|ModifiedProperties|[modifiedProperty](modifiedproperty.md) 集合|此对象上此设置操作中修改的每个属性的详细信息。|
|provisioningSteps|[provisioningStep](provisioningstep.md) 集合|设置中的每个步骤的详细信息。|
|servicePrincipal|[servicePrincipal](serviceprincipal.md) 集合|表示用于设置的服务主体。|
|sourceIdentity|[provisionedIdentity](provisionedidentity.md)|正在预配的源对象的详细信息。|
|sourceSystem|[provisioningSystemDetails](provisioningsystemdetails.md)|正在预配的对象的源系统的详细信息。|
|statusInfo|[statusBase](statusbase.md)|设置状态的详细信息。|
|targetIdentity|[provisionedIdentity](provisionedidentity.md)|正在预配的目标对象的详细信息。|
|targetSystem|[provisioningSystemDetails](provisioningsystemdetails.md)|要设置的对象的目标系统的详细信息。|
|tenantId|String|唯一的 Azure AD 租户 ID。|

## <a name="relationships"></a>关系

无。

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.provisioningObjectSummary",
  "baseType": "",
  "keyProperty": "id"
}-->

```json
{
  "action": "String",
  "activityDateTime": "String (timestamp)",
  "changeId": "String",
  "cycleId": "String",
  "durationInMilliseconds": 1024,
  "id": "String (identifier)",
  "initiatedBy": {"@odata.type": "microsoft.graph.initiator"},
  "jobId": "String",
  "modifiedProperties": [{"@odata.type": "microsoft.graph.modifiedProperty"}],
  "provisioningSteps": [{"@odata.type": "microsoft.graph.provisioningStep"}],
  "servicePrincipal": [{"@odata.type": "microsoft.graph.provisioningServicePrincipal"}],
  "sourceIdentity": {"@odata.type": "microsoft.graph.provisionedIdentity"},
  "sourceSystem": {"@odata.type": "microsoft.graph.provisioningSystemDetails"},
  "statusInfo": {"@odata.type": "microsoft.graph.statusBase"},
  "targetIdentity": {"@odata.type": "microsoft.graph.provisionedIdentity"},
  "targetSystem": {"@odata.type": "microsoft.graph.provisioningSystemDetails"},
  "tenantId": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "provisioningObjectSummary resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


