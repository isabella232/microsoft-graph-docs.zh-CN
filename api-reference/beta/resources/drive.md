---
author: JeremyKelley
ms.author: JeremyKelley
title: 驱动器资源类型
description: 表示用户的 OneDrive 或 SharePoint 中文档库的驱动器资源。
localization_priority: Priority
ms.prod: sharepoint
doc_type: resourcePageType
ms.openlocfilehash: 74ef4a5f8c2e67a81ad02ca0844d7f15dba972e8
ms.sourcegitcommit: eafb1629e52450dab0da6a1fb6d1ddfa878777c6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2020
ms.locfileid: "49081829"
---
# <a name="drive-resource-type"></a>驱动器资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

驱动器资源是代表用户的 OneDrive 或在 SharePoint 中文档库的顶级对象。

OneDrive 用户必须始终具有至少一个可用驱动器，即默认驱动器。没有 OneDrive 许可证的用户将不具有可用的默认驱动器。

## <a name="methods"></a>方法

|                        方法                              |         返回类型         | 说明 |
| :--------------------------------------------------------- | :-------------------------- |-------------|
| [获取驱动器][drive-get]                                     | 驱动器                       | 获取有关驱动器的元数据 |
| [获取驱动器根][item-get]                                 | [driveItem][]               | 获取驱动器的根文件夹 |
| [列出活动][drive-activities]                        | [itemActivity][] 集合 | 列出在驱动器下发生的活动 |
| [列出关注的项][drive-following]                     | [driveItem][] 集合    | 列出用户的关注 driveItems |
| [列出子项][item-children]                             | [driveItem][] 集合    | 列出驱动器根文件夹的子项 |
| [列出变更][item-changes]                               | [driveItem][] 集合    | 列出驱动器中所有 DriveItem 的变更 |
| [搜索][item-search]                                      | [driveItem][] 集合    | 搜索驱动器中的 DriveItem |
| [获取特殊文件夹](../api/drive-get-specialfolder.md)    | [driveItem][]               | 通过特殊文件夹的规范名称访问它 |


## <a name="properties"></a>属性

| 属性             | 类型                          | 说明                                                                                                                                                                                                                      |
| :------------------- | :---------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| createdBy            | [identitySet][]               | 识别创建项目的用户、设备或应用程序。只读。                                                                                                                                                  |
| createdDateTime      | dateTimeOffset                | 创建项的日期和时间。只读。                                                                                                                                                                                       |
| description          | String                        | 提供驱动器的用户可见说明。 读写。
| driveType            | String                        | 说明了由该资源表示的驱动器的类型。OneDrive 个人版驱动器将返回 `personal`。OneDrive for Business 将返回 `business`。SharePoint 文档库将返回 `documentLibrary`。只读。 |
| id                   | String                        | 驱动器唯一标识符。只读。                                                                                                                                                                                   |
| lastModifiedBy       | [identitySet][]               | 上次修改项目的用户、设备和应用程序的标识。只读。                                                                                                                                           |
| lastModifiedDateTime | dateTimeOffset                | 上次修改项目的日期和时间。只读。                                                                                                                                                                             |
| name                 | string                        | 项目名称。读写。                                                                                                                                                                                                |
| 所有者                | [identitySet](identityset.md) | 可选。拥有此驱动器的用户帐户。只读。                                                                                                                                                                       |
| 配额                | [配额](quota.md)             | 可选。有关驱动器的存储空间配额的信息。只读。                                                                                                                                                          |
| sharepointIds        | [sharepointIds][]             | 返回对 SharePoint REST 兼容性有用的标识符。只读。                                                                                                                                                         |
| system               | [systemFacet][]               | 如果存在，则表示这是系统管理的驱动器。 只读。
| WebUrl               | string (url)                  | 在浏览器中显示此资源的 URL。只读。                                                                                                                                                                        |

[identitySet]: identityset.md
[sharepointIds]: sharepointids.md
[systemFacet]: systemfacet.md

## <a name="relationships"></a>关系

| 关系 | 类型                                 | 说明
|:-------------|:-------------------------------------|:-----------------------
| activities   | [itemActivity][] 集合          | 最近发生在此驱动器下的活动的列表。
| 捆绑      | [driveItem][] 集合             | [捆绑][bundle] (相册和多选共享项目集) 的集合。 只在个人的 OneDrive 中。
| following    | [driveItem][] 集合             | 用户关注的项列表。 仅适用于 OneDrive for Business 中。
| items        | [driveItem][] 集合             | 驱动器中包含的所有项。只读。可为 NULL。
| root         | [driveItem][]                        | 驱动器的根文件夹。只读。
| special      | [driveItem][] 集合             | OneDrive 中可用的公用文件夹的集合。只读。可为 NULL。


## <a name="json-representation"></a>JSON 表示形式

下面是 Drive 资源的 JSON 表示形式。

**drive** 资源派生自 [**baseItem**](baseitem.md) 并继承该资源的属性。

<!--{
  "blockType": "resource",
  "optionalProperties": [
    "activities",
    "createdBy",
    "createdDateTime",
    "description",
    "lastModifiedBy",
    "lastModifiedDateTime",
    "name",
    "webUrl",
    "items",
    "root",
    "special",
    "system"
  ],
  "keyProperty": "id",
  "baseType": "microsoft.graph.baseItem",
  "@odata.type": "microsoft.graph.drive"
}-->

```json
{
  "activities": [{"@odata.type": "microsoft.graph.itemActivity"}],
  "id": "string",
  "createdBy": {"@odata.type": "microsoft.graph.identitySet"},
  "createdDateTime": "string (timestamp)",
  "description": "string",
  "driveType": "personal | business | documentLibrary",
  "following": [{"@odata.type": "microsoft.graph.driveItem"}],
  "items": [{"@odata.type": "microsoft.graph.driveItem"}],
  "lastModifiedBy": {"@odata.type": "microsoft.graph.identitySet"},
  "lastModifiedDateTime": "string (timestamp)",
  "name": "string",
  "owner": {"@odata.type": "microsoft.graph.identitySet"},
  "quota": {"@odata.type": "microsoft.graph.quota"},
  "root": {"@odata.type": "microsoft.graph.driveItem"},
  "special": [{"@odata.type": "microsoft.graph.driveItem"}],
  "system": {"@odata.type": "microsoft.graph.systemFacet"},
  "webUrl": "string",
  "sharepointIds": {"@odata.type": "microsoft.graph.sharepointIds"}
}
```


[bundle]: bundle.md
[driveItem]: driveItem.md
[itemActivity]: itemactivity.md
[item-resource]: driveitem.md
[identity-set]: identityset.md
[quota-facet]: quota.md
[drive-resource]: drive.md
[drive-activities]: ../api/activities-list.md
[drive-following]: ../api/drive-list-following.md
[drive-get]: ../api/drive-get.md
[item-get]: ../api/driveitem-get.md
[item-changes]: ../api/driveitem-delta.md
[item-search]: ../api/driveitem-search.md
[item-children]: ../api/driveitem-list-children.md


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Drive is a top level object for OneDrive API that provides access to the contents of a drive. ",
  "keywords": "drive,objects,resources",
  "section": "documentation",
  "tocPath": "Drives",
  "tocBookmarks": {
    "Resources/Drive": "#"
  },
  "suppressions": []
}
-->


