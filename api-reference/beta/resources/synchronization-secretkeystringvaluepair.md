---
title: synchronizationSecretKeyStringValuePair 资源类型
description: 表示单个机密值。
localization_priority: Normal
doc_type: resourcePageType
author: ArvindHarinder1
ms.prod: microsoft-identity-platform
ms.openlocfilehash: abe0e071c94de399cf351aecea32b51ea9c09d51
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48023868"
---
# <a name="synchronizationsecretkeystringvaluepair-resource-type"></a>synchronizationSecretKeyStringValuePair 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

表示单个机密值。 

## <a name="properties"></a>属性
| 属性     | 类型   |说明|
|:---------------|:--------|:----------|
|Key|String| 可能的值为：、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、 `None` `UserName` `Password` `SecretToken` `AppKey` `BaseAddress` `ClientIdentifier` `ClientSecret` `SingleSignOnType` `Sandbox` `Url` `Domain` `ConsumerKey` `ConsumerSecret` `TokenKey` `TokenExpiration` `Oauth2AccessToken` `Oauth2AccessTokenCreationTime` `Oauth2RefreshToken` `SyncAll` `InstanceName` `Oauth2ClientId` `Oauth2ClientSecret` `CompanyId` `UpdateKeyOnSoftDelete` `SynchronizationSchedule` `SystemOfRecord` `SandboxName` `EnforceDomain` `SyncNotificationSettings` `Server` `PerformInboundEntitlementGrants` `HardDeletesEnabled` `SyncAgentCompatibilityKey` `SyncAgentADContainer` `ValidateDomain` `TestReferences` 。|
|value|String|密码的值。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.synchronizationSecretKeyStringValuePair"
}-->

```json
{
  "key": "String",
  "value": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "synchronizationSecretKeyStringValuePair resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


