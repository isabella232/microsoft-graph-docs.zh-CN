---
title: reportRoot： getM365AppPlatformUserCounts
description: 获取一个报告，该报告为组织中的每个平台（Windows、Mac、web 和移动设备）上的所有应用提供活动用户的趋势。
localization_priority: Normal
ms.prod: reports
author: pranoychaudhuri
doc_type: apiPageType
ms.openlocfilehash: 91ae0c420bf13e967a289431799328138b9bf143
ms.sourcegitcommit: 342516a52b69fcda31442b130eb6bd7e2c8a0066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48975127"
---
# <a name="reportroot-getm365appplatformusercounts"></a>reportRoot： getM365AppPlatformUserCounts

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

获取一个报告，该报告为组织中的每个平台（Windows、Mac、web 和移动设备）上的所有应用提供活动用户的趋势。

> **注意：** 若要详细了解不同的报表视图和名称，请参阅 [microsoft 365 报表-microsoft 365 应用程序使用](/microsoft-365/admin/activity-reports/microsoft365-apps-usage)。

## <a name="permissions"></a>权限

要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

| 权限类型                        | 权限（从最低特权到最高特权） |
| :------------------------------------- | :------------------------------------------ |
| 委派（工作或学校帐户）     | Reports.Read.All                            |
| 委派（个人 Microsoft 帐户） | 不支持。                              |
| 应用                            | Reports.Read.All                            |

> **注意：** 为使应用程序代表用户读取服务使用情况报告的委派权限，租户管理员必须已为该用户分配适当的 Azure AD 有限管理员角色。 有关详细信息，请参阅 [授权 For api 以读取 Microsoft 365 使用情况报告](/graph/reportroot-authorization)。

## <a name="http-request"></a>HTTP 请求

<!-- { "blockType": "ignored" } --> 

```http
GET /reports/getM365AppPlatformUserCounts(period='{period_value}')
```

## <a name="function-parameters"></a>函数参数

在请求 URL 中，提供以下参数的有效值。

| 参数 | 类型   | 说明                                                                                                                                                                                                                                                       |
| :-------- | :----- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| period    | string | 指定在多长时间内聚合报表。 {Period_value} 支持的值为： `D7` 、 `D30` 、 `D90` 、和 `D180` 。 这些值采用格式 D *n* ，其中 *n* 表示在多少天内聚合报表。 必需。 |

## <a name="optional-query-parameters"></a>可选的查询参数

此方法支持使用 `$format` [OData 查询参数](/graph/query-parameters)自定义响应。 默认输出类型为 text/csv。 但是，如果要指定输出类型，则可以使用 OData `$format` 查询参数将默认输出设置为 text/csv 或 application/json。

## <a name="request-headers"></a>请求标头

| 名称          | 说明               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}。必需。 |

## <a name="request-body"></a>请求正文

请勿为此方法提供请求正文。

## <a name="response"></a>响应

如果成功，此方法 `200 OK` 在响应正文中返回响应代码和 [report](../resources/intune-shared-report.md) 对象。 报告数据包含在 **report** 对象的 **content** 属性中。

### <a name="csv"></a>CSV

如果成功，请求 **content** 属性将返回一个 `302 Found` 响应，该响应将重定向到报告的 preauthenticated 下载 URL。 可以在响应的 `Location` 头中找到此 URL。

预先验证的下载 URL 的有效时间很短（几分钟），不需要 `Authorization` 标头。

CSV 文件包含下面的列标题：

- 报表刷新日期
- 报表周期
- 报表日期
- Outlook
- Word
- Excel
- PowerPoint
- OneNote
- Teams

### <a name="json"></a>JSON

如果成功，请求 **content** 属性将 `200 OK` 在响应正文中返回响应代码和 JSON 对象。

## <a name="examples"></a>示例

### <a name="example-1-csv-output"></a>示例1： CSV 输出

下面是输出 CSV 的示例。

#### <a name="request"></a>请求

下面的示例显示了获取 **内容** 属性的请求。



# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "reportroot_getM365AppPlatformUserCounts_csv"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/reports/getM365AppPlatformUserCounts(period='D7')/content?$format=text/csv
```
# <a name="c"></a>[C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/reportroot-getm365appplatformusercounts-csv-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/reportroot-getm365appplatformusercounts-csv-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/reportroot-getm365appplatformusercounts-csv-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="java"></a>[Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/reportroot-getm365appplatformusercounts-csv-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---



#### <a name="response"></a>响应

下面展示了示例响应。

<!-- { "blockType": "response" } --> 

```http
HTTP/1.1 302 Found
Content-Type: text/plain
Location: https://reports.office.com/data/download/JDFKdf2_eJXKS034dbc7e0t__XDe
```

执行 302 重定向，下载的 CSV 文件将采用以下架构。

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "stream"
} -->

```http
HTTP/1.1 200 OK
Content-Type: application/octet-stream

Report Refresh Date,Report Period,Report Date,Windows,Mac,Mobile,Web
```

### <a name="example-2-json-output"></a>示例2： JSON 输出

下面是一个返回 JSON 的示例。

#### <a name="request"></a>请求

下面的示例显示了获取 **内容** 属性的请求。



# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "reportroot_getM365AppPlatformUserCounts_json"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/reports/getM365AppPlatformUserCounts(period='D7')/content?$format=application/json
```
# <a name="c"></a>[C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/reportroot-getm365appplatformusercounts-json-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/reportroot-getm365appplatformusercounts-json-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/reportroot-getm365appplatformusercounts-json-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="java"></a>[Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/reportroot-getm365appplatformusercounts-json-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---



#### <a name="response"></a>响应

下面展示了示例响应。

> **注意：** 为了提高可读性，可能缩短了此处显示的响应对象。所有属性都将通过实际调用返回。

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "stream"
} -->

```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 156

{
  "value": [
    {
      "reportRefreshDate": "2020-06-30",
      "reportPeriod": 7,
      "userCounts": [
        {
          "reportDate": "2020-06-30",
          "windows": 1445,
          "mac": 146,
          "mobile": 1131,
          "web": 1080
        }
      ]
    }
  ]
}
```
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79 
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Example",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
