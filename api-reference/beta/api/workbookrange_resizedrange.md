# <a name="workbookrange-resizedrange"></a>workbookRange: resizedRange
获取与当前范围对象类似的范围对象，但其右下角可通过一定数量的行和列进行展开（或合拢）。

### <a name="prerequisites"></a>先决条件
若要执行此 API，必须有以下**范围**：_Files.Read、Files.ReadWrite_
### <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
```http
POST /me/drive/root/workbook/worksheets/{id}/range/resizedRange(deltaRows={n}, deltaColumns={n})

```
### <a name="request-headers"></a>请求标头
| 名称       | 说明|
|:---------------|:----------|
| Authorization  | Bearer <code>|
| Workbook-Session-Id  | 确定是否保留更改的工作簿会话 ID。可选。|

### <a name="parameters"></a>参数

| 参数       | 类型    |说明|
|:---------------|:--------|:----------|
|deltarows|Int32|相对于当前范围，右下角展开的行数。使用正数可展开范围，使用负数可合拢范围|
|deltaColumns|Int32|相对于当前范围，右下角展开的列数。使用正数可展开范围，使用负数可合拢范围。|

### <a name="request-body"></a>请求正文
在请求 URL 中，提供以下查询参数（含值）。

| 参数       | 类型    |说明|
|:---------------|:--------|:----------|
|deltaRows|Int32||
|deltaColumns|Int32||

### <a name="response"></a>响应
如果成功，此方法在响应正文中返回 `200, OK` 响应代码和 [workbookRange](../resources/range.md) 对象。

### <a name="example"></a>示例
下面是一个如何调用此 API 的示例。
##### <a name="request"></a>请求
下面是一个请求示例。
<!-- {
  "blockType": "request",
  "name": "workbookrange_resizedrange"
}-->
```http
POST https://graph.microsoft.com/{ver}/drive/root/workbook/worksheets/{id}/range/resizedRange(deltarows={n}, deltaColumns={n})
```

##### <a name="response"></a>响应
下面是一个响应示例。注意：为了简单起见，可能会将此处所示的响应对象截断。将从实际调用中返回所有属性。
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.range"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 157

{
  "address": "address-value",
  "addressLocal": "addressLocal-value",
  "cellCount": 99,
  "columnCount": 99,
  "columnHidden": true,
  "columnIndex": 99
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "workbookRange: resizedRange",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
