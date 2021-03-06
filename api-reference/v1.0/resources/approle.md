---
title: appRole 资源类型
description: 表示可能由调用其他应用程序的客户端应用程序请求的应用程序角色，或可用于向指定的应用程序角色中的用户或组分配应用程序的应用程序角色。
localization_priority: Normal
doc_type: resourcePageType
ms.prod: microsoft-identity-platform
author: sureshja
ms.openlocfilehash: d094a91ca7e8b923322853fbdabcf63e65e2082d
ms.sourcegitcommit: 7370fb65d11d1347123a3f6d320d2c6d36f34224
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338163"
---
# <a name="approle-resource-type"></a>appRole 资源类型

命名空间：microsoft.graph

表示可由 (请求和授予) 客户端应用程序的应用程序角色，或可用于向指定角色中的用户或组分配应用程序的应用程序角色。 

[Application](application.md)和[ServicePrincipal](serviceprincipal.md)实体的**appRoles**属性是**appRole**的集合。 

使用 [appRoleAssignments](approleassignment.md)，可以将应用程序角色分配给用户、组或其他应用程序的服务主体。

## <a name="properties"></a>属性

| 属性   | 类型 |说明|
|:---------------|:--------|:----------|
|allowedMemberTypes|String 集合|指定是否可将此应用程序角色分配给用户和组 (通过设置为 `["User"]`) 、通过设置为 (的其他应用程序的 (，或通过设置为 `["Application"]` `["User", "Application"]`) 。 支持分配给其他应用程序的服务主体的应用程序角色也称为 " [应用程序权限](/graph/auth/auth-concepts#microsoft-graph-permissions)"。 "Application" 值仅对在 **应用程序** 实体上定义的应用程序角色受支持。|
|description|字符串|应用程序角色的说明。 在授权体验期间，如果应用程序角色是作为应用程序的权限运行的，则会显示此情况。|
|displayName|字符串|显示在应用程序角色分配和同意体验中的权限的显示名称。|
|id|Guid|**AppRoles**集合中的唯一角色标识符。 创建新的应用程序角色时，必须提供新的 Guid 标识符。 |
|isEnabled|Boolean|在创建或更新应用程序角色时，必须将其设置为 " **true** (，这是默认) 。 若要删除角色，必须首先将此设置为 **false**。  此时，在后续调用中，可能会删除此角色。|
|格式|字符串| 指定是在 [application](application.md) 对象上还是在 [servicePrincipal](serviceprincipal.md) 实体上定义应用程序角色。 不得 _包含_ 在任何 POST 或 PATCH 请求中。 只读。 |
|value|String|指定要包含在 `roles` ID 令牌中的声明中的值，以及对分配的用户或服务主体进行身份验证的访问令牌。 长度不得超过120个字符。 允许的字符包括 `:` `!` `#` `$` `%` `&` `'` `(` `)` `*` `+` `,` `-` `.` `/` `:` `;` <code>&lt;</code> `=` <code>&gt;</code> `?` `@` `[` `]` `^` `+` `_` <code>&#96;</code> `{` <code>&#124;</code> `}` `~` ，以及范围中的字符 `0-9` `A-Z` 和 `a-z` 。 不允许使用任何其他字符，包括空格字符。  |

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.appRole"
}-->

```json
{
  "allowedMemberTypes": ["string"],
  "description": "string",
  "displayName": "string",
  "id": "guid",
  "isEnabled": true,
  "origin": "string",
  "value": "string"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "appRole resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->

