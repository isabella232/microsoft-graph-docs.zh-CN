# <a name="recipient-resource-type"></a>收件人资源类型

表示事件、邮件或组帖子发送或接收端的用户的相关信息。 

## <a name="properties"></a>属性
| 属性       | 类型    |说明|
|:---------------|:--------|:----------|
|emailAddress|[EmailAddress](emailaddress.md)|收件人的电子邮件地址。|


## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.recipient"
}-->

```json
{
  "emailAddress": {"@odata.type": "microsoft.graph.emailAddress"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "recipient resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->