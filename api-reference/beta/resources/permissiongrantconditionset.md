---
title: permissionGrantConditionSet 资源类型
description: 指定包含条件的匹配规则，按照该条件将事件包括在权限授予策略中或从中排除。
localization_priority: Priority
doc_type: resourcePageType
ms.prod: microsoft-identity-platform
author: psignoret
ms.openlocfilehash: 1d04a0e7fc1570df0cfad8289f4cb0795f2dd643
ms.sourcegitcommit: 775b38baac6a4e7704d6144ef4589f2fc476bd61
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433534"
---
# <a name="permissiongrantconditionset-resource-type"></a>permissionGrantConditionSet 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

权限授予条件集用于在[权限授予策略](permissiongrantpolicy.md)中指定匹配规则，以包括或排除权限授予事件。

权限授予条件集包含几个条件。 若要将事件与权限授予条件集匹配，必须满足所有条件。

## <a name="properties"></a>属性

| 属性     | 类型 |说明|
|:---------------|:--------|:----------|
| id | String | 权限授予条件集的唯一标识符。 键。 只读。 |
| permissionClassification | 字符串 | 正在授予的权限的[权限分类](delegatedpermissionclassification.md)，或“all”，以与任何权限分类（包括未分类的权限）匹配。 默认值为“`all`”。 |
| permissionType | permissionType | 正在授予的权限的权限类型。 可能的值：`application`，适用于应用程序权限（例如应用角色）或 `delegated`，适用于代理权限。 值 `delegatedUserConsentable` 表示未由 API 发布者配置为需要管理员同意的委派权限 - 该值可以在内置权限授予策略中使用，但不能在自定义权限授予策略中使用。 必填。 |
| resourceApplication | 字符串 | 正在为其授予权限的资源应用程序（例如 API）的 **appId**，或者与任何资源应用程序或 API 匹配的 `any`。 默认值为“`any`”。 |
| permissions | String 集合 | 要与之匹配的特定许可的 **id** 值列表，或具有单一值“all”以与任何权限匹配的列表。 可以在 API 的 [** servicePrincipal**](serviceprincipal.md) 对象的 **publishedPermissionScopes** 属性中找到委派权限的 **id **。 可以在 API 的 [**servicePrincipal**](serviceprincipal.md) 对象的 **appRoles** 属性中找到应用程序权限的 **id**。 可以在 API 的 [**servicePrincipal**](serviceprincipal.md) 对象的 **resourceSpecificApplicationPermissions** 属性中找到特定于资源的应用程序权限的 **id**。 默认值为单一值“all”。 |
| clientApplicationIds | 字符串集合 | 要匹配的客户端应用程序的 **appId** 值列表，或具有单个值“all”以匹配任何客户端应用程序的列表。 默认值为单一值“all”。 |
| clientApplicationTenantIds | 字符串集合 | 在其中注册了客户端应用程序的 Azure Active Directory 租户 ID 的列表，或具有单一值“all”以与在任何租户中注册的客户端应用程序匹配的列表。 默认值为单一值“all”。 |
| clientApplicationPublisherIds | 字符串集合 | 已验证的客户端应用程序发布者的 Microsoft 合作伙伴网络 (MPN) ID 列表，或具有单一值“all”以与来自任何发布者的客户端应用程序匹配的列表。 默认值为单一值“all”。 |
| clientApplicationsFromVerifiedPublisherOnly | 布尔值 | 设置为“`true`”将仅在具有已验证发布者的客户端应用程序上进行匹配。 设置为 `false` 将在任何客户端应用上进行匹配，即使未验证发布者。 默认值为“`false`”。 |

## <a name="json-representation"></a>JSON 表示形式

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.permissionGrantConditionSet"
}-->

```json
{
    "id": "string (identifier)",
    "permissionClassification": "string",
    "permissionType": "string",
    "resourceApplication": "string",
    "permissions": [ "string" ],
    "clientApplicationIds": [ "string" ],
    "clientApplicationTenantIds": [ "string" ],
    "clientApplicationPublisherIds": [ "string" ],
    "clientApplicationsFromVerifiedPublisherOnly": false
}
```
