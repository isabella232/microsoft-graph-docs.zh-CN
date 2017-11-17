# <a name="get-workbookpivottable"></a>Get workbookPivotTable

检索 workbookPivotTable 对象的属性和关系。

### <a name="prerequisites"></a>先决条件
若要执行此 API，必须有以下**范围**：_Files.Read、Files.ReadWrite_

### <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
```http
GET /me/drive/root/workbook/worksheets/{id}/pivotTables/{id}
```
### <a name="optional-query-parameters"></a>可选的查询参数
此方法支持 [OData 查询参数](http://developer.microsoft.com/en-us/graph/docs/overview/query_parameters) 来帮助自定义响应。

### <a name="request-headers"></a>请求标头
| 名称      |说明|
|:----------|:----------|
| Authorization  | Bearer <code>|
| Workbook-Session-Id  | 确定是否保留更改的工作簿会话 ID。可选。|

### <a name="request-body"></a>请求正文
请勿提供此方法的请求正文。
### <a name="response"></a>响应
如果成功，此方法在响应正文中返回 `200 OK` 响应代码和 [workbookPivotTable](../resources/workbookpivottable.md) 对象。
### <a name="example"></a>示例
##### <a name="request"></a>请求
下面是一个请求示例。
<!-- {
  "blockType": "request",
  "name": "get_workbookpivottable"
}-->
```http
GET https://graph.microsoft.com/{ver}/drive/root/workbook/worksheets/{id}/pivotTables/{id}
```
##### <a name="response"></a>响应
下面是一个响应示例。注意：为了简单起见，可能会将此处所示的响应对象截断。将从实际调用中返回所有属性。
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.workbookPivotTable"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 46

{
  "id": "id-value",
  "name": "name-value"
}
```
