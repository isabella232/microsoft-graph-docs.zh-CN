---
title: connectedOrganization 资源类型
description: 在 Azure AD 权限管理中，连接的组织是对其他组织的目录或域的引用，用户可以请求访问它。
author: markwahl-msft
localization_priority: Normal
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: 95cce32d4336c34a61d6845b74e6e428d1774d21
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48027207"
---
# <a name="connectedorganization-resource-type"></a>connectedOrganization 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

在 [AZURE AD 权限管理](entitlementmanagement-root.md)中，连接的组织是对其他组织的目录或域的引用，用户可以请求访问它。

## <a name="methods"></a>方法

|方法|返回类型|说明|
|:---|:---|:---|
|[列出 connectedOrganizations](../api/connectedorganization-list.md) | [connectedOrganization](connectedorganization.md) 集合 | 检索 connectedOrganization 对象的列表。 |
|[创建 connectedOrganization](../api/connectedorganization-post.md) | [connectedOrganization](connectedorganization.md) | 创建新的 connectedOrganization 对象。 |
|[获取 connectedOrganization](../api/connectedorganization-get.md) | [connectedOrganization](connectedorganization.md) | 读取 connectedOrganization 对象的属性和关系。 |
|[更新 connectedOrganization](../api/connectedorganization-update.md) | | 更新 connectedOrganization。 |
|[删除 connectedOrganization](../api/connectedorganization-delete.md) |无 | 删除 connectedOrganization。 |
|[列出 internalSponsors](../api/connectedorganization-list-internalsponsors.md) | [directoryObject](directoryobject.md) collection | 检索 connectedOrganization 的内部发起人列表。 |
|[列出 externalSponsors](../api/connectedorganization-list-externalsponsors.md) | [directoryObject](directoryobject.md) collection | 检索 connectedOrganization 的外部发起人列表。 |
|[添加 internalSponsors](../api/connectedorganization-post-internalsponsors.md) | 无 | 将用户或组添加到 connectedOrganization 的内部发起人。 |
|[添加 externalSponsors](../api/connectedorganization-post-externalsponsors.md) | 无 | 将用户或组添加到 connectedOrganization 的外部发起人。 |
|[删除 internalSponsors](../api/connectedorganization-delete-internalsponsors.md) | 无 | 从 connectedOrganization 的内部发起人中删除用户或组。 |
|[删除 externalSponsors](../api/connectedorganization-delete-externalsponsors.md) | 无 | 从 connectedOrganization 的外部发起人中删除用户或组。 |

## <a name="properties"></a>属性

|属性|类型|说明|
|:---|:---|:---|
|createdBy|String|创建此资源的用户的 UPN。 只读。|
|createdDateTime|DateTimeOffset|时间戳类型表示采用 ISO 8601 格式的日期和时间信息，始终采用 UTC 时间。 例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`。 只读。|
|说明|String|所连接的组织的说明。|
|displayName|String|所连接的组织的显示名称。|
|id|String| 只读。|
|modifiedBy|String|上次修改此资源的用户的 UPN。 只读。|
|modifiedDateTime|DateTimeOffset|时间戳类型表示采用 ISO 8601 格式的日期和时间信息，始终采用 UTC 时间。 例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`。 只读。|
|state|connectedOrganizationState|已连接组织的状态定义了请求者范围类型的工作分配策略是否 `AllConfiguredConnectedOrganizationSubjects` 适用。 可取值为：`configured`、`proposed`。|

## <a name="relationships"></a>关系

|关系|类型|说明|
|:---|:---|:---|
|identitySources|[identitySource](identitySource.md) 集合| 此连接组织中的标识源、 [azureActiveDirectoryTenant](azureactivedirectorytenant.md)、 [domainIdentitySource](domainidentitysource.md) 或 [externalDomainFederation](externaldomainfederation.md)之一。 只读。 可为空。|
|internalSponsors| [directoryObject](directoryobject.md) collection| 可为空。|
|externalSponsors| [directoryObject](directoryobject.md) collection| 可为 Null。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.connectedOrganization",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->

```json
{
  "id": "String (identifier)",
  "displayName": "String",
  "description": "String",
  "createdBy": "String",
  "createdDateTime": "String (timestamp)",
  "modifiedBy": "String",
  "modifiedDateTime": "String (timestamp)",
  "identitySources": [
    {
      "@odata.type": "microsoft.graph.azureActiveDirectoryTenant",
      "tenantId": "String (identifier)",
      "displayName": "String"
    }
  ],
  "state": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "connectedOrganization resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


