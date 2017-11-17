# <a name="sortfield-resource-type"></a>SortField 资源类型

表示排序操作中的条件。

## <a name="properties"></a>属性
| 属性       | 类型    |说明|
|:---------------|:--------|:----------|
|ascending|boolean|表示是否以升序方式进行排序。|
|color|string|表示按字体或单元格颜色进行排序时，条件的目标颜色。|
|dataOption|string|表示此字段的其他排序选项。可能的值是：`Normal`、`TextAsNumber`。|
|Key|int|表示条件所在的列（或行，具体取决于排序方向）。表示与第一列（或行）的偏移量。|
|sortOn|string|表示此条件的排序类型。可能的值是：`Value`、`CellColor`、`FontColor`、`Icon`。|

## <a name="relationships"></a>关系
| 关系 | 类型    |说明|
|:---------------|:--------|:----------|
|icon|[Icon](icon.md)|表示对单元格图标进行排序时，条件的目标图标。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.sortField"
}-->

```json
{
  "ascending": true,
  "color": "string",
  "dataOption": "string",
  "key": 1024,
  "sortOn": "string"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "SortField resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->