# <a name="sharepointids-resource-type"></a>SharePointIds 资源类型

**SharePointIds** 资源将存储在 SharePoint 网站或 OneDrive for Business 中的项的各种标识符分组到一个单一结构。

**注意：**OneDrive 个人版返回的项将不包括 **SharePointIds** 方面。

### <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [  ],
  "@odata.type": "microsoft.graph.sharepointIds"
}-->
```json
{
    "listId": "string",
    "listItemId": "string",
    "listItemUniqueId": "string",
    "siteId": "string",
    "webId": "string"
}
```

### <a name="properties"></a>属性

| 属性          | 类型    | 说明                                                          |
|:------------------|:--------|:---------------------------------------------------------------------|
| listId            | string  | SharePoint 中的项列表的唯一标识符。                          |
| listItemId        | string  | 包含列表中的项的整数标识符。                    |
| listItemUniqueId  | string  | OneDrive for Busienss 或 SharePoint 网站中的项的唯一标识符。 |
| siteId            | string  | 项的网站集合的唯一标识符。 |
| webId             | string  | 项的网站的唯一标识符。                          |

## <a name="remarks"></a>注解 

有关 DriveItem 上 facet 的详细信息，请参阅 [DriveItem](driveitem.md)。



<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "sharepointIds resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
