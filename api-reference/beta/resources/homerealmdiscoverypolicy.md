---
title: homeRealmDiscoveryPolicy 资源类型
description: 表示用于控制联合用户的 Azure Active Directory 身份验证行为的策略。
localization_priority: Normal
author: hpsin
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: 1892770838b426174589d1b9607647219342751b
ms.sourcegitcommit: a9720ab80625a4692f7d2450164717853535d0b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993932"
---
# <a name="homerealmdiscoverypolicy-resource-type"></a>homeRealmDiscoveryPolicy 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示用于控制联盟用户的 Azure Active Directory 身份验证行为的策略，尤其适用于联合域中的自动加速和用户身份验证限制。 您可以为组织中的所有服务主体或组织中的特定服务主体设置 homeRealmDiscoveryPolicy。  有关详细情况和策略的详细信息，请参阅使用主领域发现策略和[使用电子邮件作为备用登录 ID 登录 Azure Active Directory](/azure/active-directory/authentication/howto-authentication-use-email-signin)，为[应用程序配置 Azure AD 登录行为](/azure/active-directory/manage-apps/configure-authentication-for-federated-users-portal)。

继承自 [stsPolicy](stsPolicy.md)。

## <a name="methods"></a>方法

| 方法       | 返回类型 | 说明 |
|:-------------|:------------|:------------|
| [创建 homeRealmDiscoveryPolicy](../api/homerealmdiscoverypolicy-post-homerealmdiscoverypolicies.md) | [homeRealmDiscoveryPolicy](homerealmdiscoverypolicy.md) | 创建 homeRealmDiscoveryPolicy 对象。 |
| [获取 homeRealmDiscoveryPolicy](../api/homerealmdiscoverypolicy-get.md) | [homeRealmDiscoveryPolicy](homerealmdiscoverypolicy.md) | 读取 homeRealmDiscoveryPolicy 对象的属性和关系。 |
| [列出 homeRealmDiscoveryPolicy](../api/homerealmdiscoverypolicy-list.md) | [homeRealmDiscoveryPolicy](homerealmdiscoverypolicy.md) | 读取 homeRealmDiscoveryPolicies 对象的属性和关系。 |
| [更新 homeRealmDiscoveryPolicy](../api/homerealmdiscoverypolicy-update.md) | 无 | 更新 homeRealmDiscoveryPolicy 对象。 |
| [删除 homeRealmDiscoveryPolicy](../api/homerealmdiscoverypolicy-delete.md) | 无 | 删除 homeRealmDiscoveryPolicy 对象。 |
| [列出 appliesTo](../api/homerealmdiscoverypolicy-list-appliesto.md) | [directoryObject](directoryobject.md) 集合 | 获取已应用此策略的 directoryObjects 的列表。 |
| [分配 homeRealmDiscoveryPolicy](../api/serviceprincipal-post-homerealmdiscoverypolicies.md) | 无 | 将 homeRealmDiscoveryPolicy 对象分配给 [servicePrincipal](serviceprincipal.md) 对象。 |
| [列表已分配 homeRealmDiscoveryPolicy](../api/serviceprincipal-list-homerealmdiscoverypolicies.md) | [homeRealmDiscoveryPolicy](homerealmdiscoverypolicy.md) 集合 | 列出分配给 [servicePrincipal](serviceprincipal.md) 对象的 homeRealmDiscoveryPolicy 对象。 |
| [删除 homeRealmDiscoveryPolicy](../api/serviceprincipal-delete-homerealmdiscoverypolicies.md) | 无 | 从 [servicePrincipal](serviceprincipal.md) 对象中删除一个 homeRealmDiscoveryPolicy 对象。 |

## <a name="properties"></a>属性

| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|id|字符串| 此策略的唯一标识符。 只读。|
|定义|String 集合| 一个包含 JSON 字符串的字符串集合，该字符串定义此策略的规则和设置。 有关此属性的 JSON 架构的更多详细信息，请参阅下文。 必需。|
|description|字符串| 此策略的说明。|
|displayName|字符串| 此策略的显示名称。 必需。|
|isOrganizationDefault|Boolean|如果设置为 true，则激活此策略。 对于同一策略类型，可以有多个策略，但只有一个策略可以作为组织默认激活。 可选，默认值为 false。|


### <a name="properties-of-a-home-realm-discovery-policy-definition"></a>主领域发现策略定义的属性
下面的属性构成了表示令牌生存期策略的 JSON 对象。 此 JSON 对象必须 **转换为转义了引号的字符串** ，以将其插入到 **定义** 属性中。 下面以 JSON 格式显示了一个示例：

<!-- {
  "blockType": "ignored"
}-->
``` json
"definition": [
    "{\"HomeRealmDiscoveryPolicy\":
     {\"AccelerateToFederatedDomain\":true,
      \"PreferredDomain\":\"federated.example.edu\",
      \"AlternateIdLogin\":{\"Enabled\":true}}}"
  ]
```

| 属性     | 类型   |说明| 
|:---------------|:--------|:----------|
|AccelerateToFederatedDomain|Boolean| 如果设置为 `true` ，则自动加速 (绕过主页领域发现) 。 如果 `true` 在租户中只有一个经过验证和联合的域，则用户将直接转到联合身份提供程序 (如用于登录的 ADFS) 。 如果 `true` 租户中有多个已验证的域，则必须指定 **PreferredDomain** 。 可选。|
|PreferredDomain|字符串| 指定要加速登录到的域。 如果租户只有一个联合域，则可以省略它。 如果省略它，并且有多个经过验证的联合域，则此策略将不起作用。 如果 **AccelerateToFederatedDomain** 为，则为必需 `true` 。|
|AllowCloudPasswordValidation|Boolean| 设置为 `true` 以允许应用程序通过直接向 Azure Active Directory 令牌终结点提供用户名/密码凭据来对联合用户进行身份验证。 仅在启用密码哈希同步时才有效。 可选。|
|AlternateIdLogin| Json |设置为 {"Enabled"： true} 以允许 Azure AD 登录使用电子邮件作为 [备用登录 ID](/azure/active-directory/authentication/howto-authentication-use-email-signin)。 仅在将 **IsOrganizationDefault** 设置为时起作用 `true` 。 可选。|

## <a name="relationships"></a>关系

| 关系 | 类型        | 说明 |
|:-------------|:------------|:------------|
|appliesTo|[directoryObject](directoryobject.md) 集合| 已将此策略应用于的 [directoryObject](directoryObject.md) 集合。 只读。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.homeRealmDiscoveryPolicy",
  "baseType": "",
  "keyProperty": "id"
}-->

```json
{
  "definition": ["String"],
  "description": "String",
  "displayName": "String",
  "id": "String (identifier)",
  "isOrganizationDefault": true
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "homeRealmDiscoveryPolicy resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
