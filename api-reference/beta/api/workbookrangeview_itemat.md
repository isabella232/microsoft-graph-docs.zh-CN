# <a name="workbookrangeview-itemat"></a>workbookRangeView: itemAt


### <a name="prerequisites"></a>先决条件
要执行此 API，需要以下**范围**：
### <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
```http
GET me/drive/root/workbook/worksheets/{id}/range(addres={address})/visibleView/itemAt(index={n})

```
### <a name="request-headers"></a>请求标头
| 名称       | 说明|
|:---------------|:----------|
| Authorization  | Bearer {code}|
| Workbook-Session-Id  | 确定是否保留更改的工作簿会话 ID。可选。|

### <a name="request-body"></a>请求正文
在请求 URL 中，提供以下查询参数（含值）。

| 参数       | 类型    |说明|
|:---------------|:--------|:----------|
|index|Int32|要返回的项的索引。|

### <a name="response"></a>响应
如果成功，此方法在响应正文中返回 `200, OK`响应代码和 [workbookRangeView](../resources/workbookrangeview.md) 对象。

### <a name="example"></a>示例
下面是一个如何调用此 API 的示例。
##### <a name="request"></a>请求
下面是一个请求示例。
<!-- {
  "blockType": "request",
  "name": "workbookrangeview_itemat"
}-->
```http
GET https://graph.microsoft.com/{ver}/drive/root/workbook/worksheets/{id}/range(addres='A1:Z10')/visibleView/itemAt(index=0)

```

##### <a name="response"></a>响应
下面是一个响应示例。注意：为了简单起见，可能会将此处所示的响应对象截断。将从实际调用中返回所有属性。
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.workbookRangeView"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 194

{
  "cellAddresses": "cellAddresses-value",
  "columnCount": 99,
  "formulas": "formulas-value",
  "formulasLocal": "formulasLocal-value",
  "formulasR1C1": "formulasR1C1-value",
  "index": 99
}
```
