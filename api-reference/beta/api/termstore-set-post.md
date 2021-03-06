---
title: 创建集
description: 创建新的 set 对象。
author: mohitpcad
localization_priority: Normal
ms.prod: Sharepoint
doc_type: apiPageType
ms.openlocfilehash: ecf1327333ddd9a38d3199c01a0c6b2436eb27a2
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48064586"
---
# <a name="create-set"></a>创建集
命名空间： termStore

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

创建新的 [set](../resources/termstore-set.md) 对象。

## <a name="permissions"></a>权限
要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

|权限类型|权限（从最高特权到最低特权）|
|:---|:---|
|委派（工作或学校帐户） |TermStore.ReadWrite.All |
|委派（个人 Microsoft 帐户） | 不支持。    |
|应用程序 | 不支持。 |


## <a name="http-request"></a>HTTP 请求

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /termStore/sets
```

## <a name="request-headers"></a>请求标头
|名称|说明|
|:---|:---|
|Authorization|Bearer {token}。必需。|
|Content-Type|application/json. Required.|

## <a name="request-body"></a>请求正文
在请求正文中，提供 [set](../resources/termstore-set.md) 对象的 JSON 表示形式。

下表显示创建 [集](../resources/termstore-set.md)时所需的属性。

|属性|类型|说明|
|:---|:---|:---|
|localizedNames|[termstore](../resources/termstore-localizedname.md) 集合的 localizedName|要创建的集的名称|
|parentGroup|[termstore 的组](../resources/termstore-group.md)|需要在其下创建集的 termstore 组|



## <a name="response"></a>响应

如果成功，此方法 `201 Created` 在响应正文中返回响应代码和 [set](../resources/termstore-set.md) 对象。

## <a name="examples"></a>示例

### <a name="request"></a>请求
``` http
POST https://graph.microsoft.com/beta/termStore/sets
Content-Type: application/json
Content-length: 288

{
  "@odata.type": "#microsoft.graph.termStore.set",
  "parentGroup":{
      "id": "fc733b51-10f1-40fd-b784-dc6d1e42804b"
   },
   "localizedNames" : [
      {
        "languageTag" : "en-US",
        "name" : "Department"
      }
  ]
}
```


### <a name="response"></a>响应
**注意：** 为了提高可读性，可能缩短了此处显示的响应对象。
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.termstore.set"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json
{
  "@odata.type": "#microsoft.graph.termStore.set",
  "id": "3607e9f9-e9f9-3607-f9e9-0736f9e90736",
  "localizedNames" : [
      {
        "languageTag" : "en-US",
        "name" : "Department"
      }
  ]
}
```


[microsoft.graph.termStore.set]: ../resources/termstore-set.md
[microsoft.graph.termStore.group]: ../resources/termstore-group.md
[microsoft.graph.termStore.term]: ../resources/termstore-term.md

<!--
{
  "type": "#page.annotation",
  "description": "Create a termSet entity in termStore",
  "keywords": "term,termStore",
  "section": "documentation",
  "tocPath": "termStore/Create termSet",
  "suppressions": [
  ]
}
-->


