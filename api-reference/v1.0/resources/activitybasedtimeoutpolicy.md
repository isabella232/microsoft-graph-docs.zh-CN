---
title: activityBasedTimeoutPolicy 资源类型
description: 表示一个策略，该策略可控制支持基于活动的超时功能的应用程序的 web 会话的空闲超时。
localization_priority: Normal
author: lujiangfeng666
ms.prod: microsoft-identity-platform
doc_type: resourcePageType
ms.openlocfilehash: 91c8d3933f9ec1fe8e96a5f62c9d00791ffe4777
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48003378"
---
# <a name="activitybasedtimeoutpolicy-resource-type"></a>activityBasedTimeoutPolicy 资源类型

命名空间：microsoft.graph

表示一个策略，该策略可控制支持基于活动的超时功能的应用程序的 web 会话的空闲超时。 应用程序在处于非活动状态一段时间后强制自动 signout。 通过将 **isOrganizationDefault** 属性设置为) ，只能在组织级别 (应用此类型的策略 `true` 。

继承自 [stsPolicy](stsPolicy.md)。

## <a name="methods"></a>方法

| 方法       | 返回类型 | 说明 |
|:-------------|:------------|:------------|
| [列出 activityBasedTimeoutPolicies](../api/activitybasedtimeoutpolicy-list.md) | [activityBasedTimeoutPolicy](activitybasedtimeoutpolicy.md) | 读取 activityBasedTimeoutPolicy 对象的属性和关系。 |
| [创建 activityBasedTimeoutPolicy](../api/activitybasedtimeoutpolicy-post-activitybasedtimeoutpolicies.md) | [activityBasedTimeoutPolicy](activitybasedtimeoutpolicy.md) | 创建 activityBasedTimeoutPolicy 对象。 |
| [获取 activityBasedTimeoutPolicy](../api/activitybasedtimeoutpolicy-get.md) | [activityBasedTimeoutPolicy](activitybasedtimeoutpolicy.md) | 读取 activityBasedTimeoutPolicy 对象的属性和关系。 |
| [更新 activityBasedTimeoutPolicy](../api/activitybasedtimeoutpolicy-update.md) | 无 | 更新 activityBasedTimeoutPolicy 对象。 |
| [删除 activityBasedTimeoutPolicy](../api/activitybasedtimeoutpolicy-delete.md) | 无 | 删除 activityBasedTimeoutPolicy 对象。 |

## <a name="properties"></a>属性

| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|id|String| 此策略的唯一标识符。 只读。|
|定义|String collection| 一个包含 JSON 字符串的字符串集合，该字符串定义此策略的规则和设置。 有关此属性的 JSON 架构的更多详细信息，请参阅下文。 必需。|
|description|String| 此策略的说明。|
|displayName|String| 此策略的显示名称。 必需。|
|isOrganizationDefault|Boolean|如果设置为 true，则激活此策略。 对于同一策略类型，可以有多个策略，但只有一个策略可以作为组织默认激活。 可选，默认值为 false。|


### <a name="properties-of-an-activity-based-timeout-policy-definition"></a>基于活动的超时策略定义的属性
下面的属性构成了表示基于活动的超时策略的 JSON 对象。 此 JSON 对象必须 **转换为转义了引号的字符串** ，以将其插入到 **定义** 属性中。 下面以 JSON 格式显示了一个示例：

<!-- {
  "blockType": "ignored"
}-->
```json
{
  "definition":["{\"ActivityBasedTimeoutPolicy\":{\"Version\":1,\"ApplicationPolicies\":[{\"ApplicationId\":\"default\",\"WebSessionIdleTimeout\":\"01:00:00\"},{\"ApplicationId\":\"c44b4083-3bb0-49c1-b47d-974e53cbdf3c\",\"WebSessionIdleTimeout\":\"00:15:00\"}]}}"]
}
```

>**注意：** 这些属性中的所有持续时间均以 "dd. hh： mm： ss" 的格式指定。

>**注意：** "天" 中表示的属性的最大值是表示的天数的1秒。 例如，"最大值为1天" 指定为 "23:59:59"。

| 属性     | 类型   |说明|
|:-------------|:------|:---------|
|版本|整数|策略版本。 将值设置为1。 必需。|
|ApplicationPolicies|JSON 对象|应用程序策略的集合。 应用程序策略是 ApplicationId 和 WebSessionIdleTimeout 的组合： <br> <ul><li>**ApplicationId**：允许的值：<ul><li> 默认：将策略应用于所有支持基于活动的超时功能但不具有特定于应用程序的替代的应用程序</li><li> c44b4083-3bb0-49c1-b47d-974e53cbdf3c：将策略应用于 Azure 门户</li></ul></li><li>**WebSessionIdleTimeout**：用户的 web 会话被认为已过期的用户非活动时段。 最小值为5分钟;最大值为1天。</li></ul> |


## <a name="relationships"></a>关系

无

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.activityBasedTimeoutPolicy",
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
  "description": "activityBasedTimeoutPolicy resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

