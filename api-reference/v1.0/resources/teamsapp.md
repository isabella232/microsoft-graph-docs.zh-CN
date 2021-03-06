---
title: teamsApp 资源类型
description: Microsoft Teams 应用对话框中的应用。
author: nkramer
localization_priority: Priority
ms.prod: microsoft-teams
doc_type: resourcePageType
ms.openlocfilehash: bf9c152de12acc31ecf13100c6dcba753d1d476b
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48036938"
---
# <a name="teamsapp-resource-type"></a>teamsApp 资源类型

命名空间：microsoft.graph

代表[Microsoft Teams](teams-api-overview.md) 应用目录中的一个应用.

用户可以在 Microsoft Teams 商店中看到这些应用，并且可以使用“[向团队添加应用](../api/teamsappinstallation-add.md)”方法将这些应用安装到 [Teams](team.md) 中。

## <a name="methods"></a>方法

| 方法       | 返回类型  |说明|
|:---------------|:--------|:----------|
|[列出已发布的应用](../api/teamsapp-list.md) | [teamsApp](teamsapp.md) 集合 | 列出 Microsoft Teams 应用目录中已发布的应用。|
|[发布应用](../api/teamsapp-publish.md) | [teamsApp](teamsapp.md) | 将应用发布到组织的应用目录。|
|[更新已发布的应用](../api/teamsapp-update.md) | [teamsApp](teamsapp.md) | 更新组织应用目录中的已发布应用。|
|[删除已发布的应用](../api/teamsapp-delete.md) | 无 | 更新组织应用目录中已发布的应用。|

## <a name="properties"></a>属性

| 属性            | 类型     | 说明 |
|:------------------- |:-------- |:----------- |
| id                  | string   | 目录应用生成的应用 ID（不同于开发人员在 [Microsoft Teams 应用压缩包](/microsoftteams/platform/concepts/apps/apps-package)中提供的 ID）。 |
| externalId          | string   | 应用开发人员在 [Microsoft Teams 应用压缩包](/microsoftteams/platform/concepts/apps/apps-package)中提供的目录 ID。 |
| displayName                | string   | 应用开发人员在 [Microsoft Teams 应用压缩包](/microsoftteams/platform/concepts/apps/apps-package)中提供的目录名称。 |
| distributionMethod  | teamsAppDistributionMethod     | 应用的分配方法。 只读。|

### <a name="teamsappdistributionmethod-values"></a>teamsAppDistributionMethod 值

|成员|值|说明|
|:---|:---|:---|
|商店|0| 应用适用于 Microsoft Teams 应用商店中的所有租户。|
|组织|1|应用仅适用于此租户。|
|旁加载|2|应用仅适用于安装它的用户/团队。|

## <a name="relationships"></a>关系

| 关系 | 类型   | 说明 |
|:---------------|:--------|:----------|
|appDefinitions|[teamsAppDefinition](teamsappdefinition.md) 集合| 每个版本的应用的详细信息。 |

## <a name="json-representation"></a>JSON 表示形式

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.teamsApp",
  "baseType": "microsoft.graph.entity"
}-->

```json
{
  "id": "string",
  "externalId": "string",
  "displayName": "string",
  "distributionMethod": "string"
}
```

## <a name="see-also"></a>另请参阅

- [teamsAppInstallation](teamsappinstallation.md)
- [teamsAppDefinition](teamsappdefinition.md)
- [teamsTab](../resources/teamstab.md)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "teamsApp resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


