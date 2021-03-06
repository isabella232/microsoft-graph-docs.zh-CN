---
title: privilegedRoleAssignmentRequest 资源类型
description: 表示在 Privilegd 标识管理中对角色分配操作的请求。
localization_priority: Normal
doc_type: resourcePageType
ms.prod: microsoft-identity-platform
author: shauliu
ms.openlocfilehash: 5daeeee6f784c31f1e15843a8a1903ca41565118
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48070508"
---
# <a name="privilegedroleassignmentrequest-resource-type"></a>privilegedRoleAssignmentRequest 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示在 Privilegd 标识管理中对角色分配操作的请求。

`privilegedRoleAssignmentRequest` 是用于管理角色分配生命周期的票据建模实体。 它表示用户和管理员的意向/决定，还提供了灵活的功能，可以实现定期 schduling、审批门等，与直接公开 `POST` 和 `LIST` 运营以及 `MY` 和 `Cancel` 上的功能相比 `governanceRoleAssignment` 。

## <a name="methods"></a>方法

| 方法       | 返回类型 | Description |
|:-------------|:------------|:------------|
|[List](../api/privilegedroleassignmentrequest-list.md) | [privilegedroleassignmentrequest](../resources/privilegedroleassignmentrequest.md)  集合|列出角色分配请求。|
|[Create](../api/privilegedroleassignmentrequest-post.md)|  [privilegedroleassignmentrequest](../resources/privilegedroleassignmentrequest.md)|创建一个请求，以管理现有或新角色分配的生命周期。|
|[Cancel](../api/privilegedroleassignmentrequest-cancel.md)|  |取消挂起的角色分配请求。|
|[My](../api/privilegedroleassignmentrequest-my.md)|  |获取当前 requstor 的角色分配请求。|

## <a name="properties"></a>属性

| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|id|String| 只读。 角色分配请求的 id。|
|assignmentState|String| 工作分配的状态。 此值可 `Eligible` 用于符合条件的工作分配 `Active` -如果是由管理员直接分配的 `Active` ，或者是由用户的符合条件的工作分配激活的。|
|duration|String| 角色分配的持续时间。|
|reason|String| 角色分配的原因。|
|requestedDateTime|DateTimeOffset| 只读。 请求创建时间。 时间戳类型表示采用 ISO 8601 格式的日期和时间信息，始终采用 UTC 时区。 例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`。|
|roleId|String| 角色的 id。|
|schedule|[governanceSchedule](governanceschedule.md)| 角色分配请求的 schedule 对象。|
|状态|String| 只读。角色分配请求的状态。 值可以是、、、、、、、、、 `NotStarted` `Completed` `RequestedApproval` `Scheduled` `Approved` `ApprovalDenied` `ApprovalAborted` `Cancelling` `Cancelled` `Revoked` 、 `RequestExpired` 。|
|ticketNumber|String| 角色分配的 ticketNumber。 |
|ticketSystem|String| 角色分配的 ticketSystem。|
|type|String| 表示角色分配上操作的类型。 值可以是 `AdminAdd` ： Administrators 将用户添加到角色; `UserAdd` ：用户添加角色分配。|
|userId|String| 用户的 id。|

## <a name="relationships"></a>关系
| 关系 | 类型        | 说明 |
|:-------------|:------------|:------------|
|roleInfo|[privilegedRole](privilegedrole.md)| 角色分配请求的 roleInfo 对象。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.privilegedRoleAssignmentRequest"
}-->

```json
{
  "assignmentState": "String",
  "duration": "String",
  "id": "String (identifier)",
  "reason": "String",
  "requestedDateTime": "String (timestamp)",
  "roleId": "String",
  "schedule": {"@odata.type": "microsoft.graph.governanceSchedule"},
  "status": "String",
  "ticketNumber": "String",
  "ticketSystem": "String",
  "type": "String",
  "userId": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "privilegedRoleAssignmentRequest resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


