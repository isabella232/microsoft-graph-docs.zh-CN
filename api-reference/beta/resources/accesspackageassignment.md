---
title: accessPackageAssignment 资源类型
description: 访问包分配是一段时间内特定主题的访问包的分配。
localization_priority: Normal
author: markwahl-msft
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: fd85461a4429801aad5145256c711278789c95ed
ms.sourcegitcommit: bbb617f16b40947769b262e6e85f0dea8a18ed3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "49000705"
---
# <a name="accesspackageassignment-resource-type"></a>accessPackageAssignment 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

在 [AZURE AD 权限管理](entitlementmanagement-root.md)中，访问包分配是一段时间内特定主题的访问包分配。  例如，访问包分配可以声明用户 Alice 已通过访问包 Sales （2019年1月1日至7月2019）分配了访问权限。

## <a name="methods"></a>方法

| 方法       | 返回类型 | 说明 |
|:-------------|:------------|:------------|
| [列出 accessPackageAssignments](../api/accesspackageassignment-list.md) | [accessPackageAssignment](accesspackageassignment.md) 集合 | 检索 **accesspackageassignment** 对象的列表。 |

>**注意：** 不能使用方法来创建或删除访问包分配。 相反，要为用户请求访问包分配或从用户中删除访问包分配的客户端，可以 [创建 accessPackageAssignmentRequest](../api/accesspackageassignmentrequest-post.md)。

## <a name="properties"></a>属性

| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|accessPackageId|字符串|访问包的标识符。 只读。|
|assignmentPolicyId|字符串|访问包分配策略的标识符。 只读。|
|assignmentState|字符串|访问包分配的状态。 可能的值为 `Delivering` 、 `Delivered` 或 `Expired` 。 只读。|
|assignmentStatus|字符串|有关工作分配生命周期的详细信息。  可能的值包括 `Delivering` 、 `Delivered` 、 `NearExpiry1DayNotificationTriggered` 或 `ExpiredNotificationTriggered` 。  只读。|
|catalogId|字符串|包含访问包的目录的标识符。 只读。|
|expiredDateTime|DateTimeOffset|时间戳类型表示使用 ISO 8601 格式的日期和时间信息，并且始终处于 UTC 时间。例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`|
|id|字符串| 只读。|
|isExtended|Boolean|指示访问包分配是否已扩展。 只读。|
|targetId|字符串| 包含工作分配的主题的 ID。 只读。|
|schedule|[requestSchedule](requestschedule.md)| 当访问工作分配准备就绪时。 只读。|

## <a name="relationships"></a>关系

| 关系 | 类型        | 说明 |
|:-------------|:------------|:------------|
|accessPackage|[accessPackage](accesspackage.md)| 只读。 可为 Null。|
|accessPackageAssignmentPolicy|[accessPackageAssignmentPolicy](accesspackageassignmentpolicy.md)| 只读。 可为 Null。|
|accessPackageAssignmentResourceRoles|[accessPackageAssignmentResourceRole](accesspackageassignmentresourcerole.md) 集合| 为此分配传递给目标用户的资源角色。 只读。 可为 Null。|
|target|[accessPackageSubject](accesspackagesubject.md)| 访问包分配的主题。 只读。 可为 Null。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.accessPackageAssignment",
  "baseType": "",
  "keyProperty": "id"
}-->

```json
{
   "id":"9bdae7b4-6ece-487b-9eb8-9679dbd67aa2",
   "catalogId":"cc30dc98-6d3c-4fa0-bed8-fd76d0efd993",
   "accessPackageId":"e3f47362-993f-4fcb-8a38-532ffca16150",
   "assignmentPolicyId":"63ebd106-8116-40e7-a0ab-01ae475d11bb",
   "targetId":"ab4291f6-66b7-42bf-b597-a05b29414f5c",
   "assignmentStatus":"ExpiredNotificationTriggered",
   "assignmentState":"Expired",
   "isExtended":false,
   "expiredDateTime":"2019-04-25T23:45:40.42Z"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "accessPackageAssignment resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


