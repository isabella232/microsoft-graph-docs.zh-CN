---
title: 更新 deviceManagementReportSchedule
description: 更新 deviceManagementReportSchedule 对象的属性。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: apiPageType
ms.openlocfilehash: 8c4060ab349207a1c364320cba3ec1491e3e78b4
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49307750"
---
# <a name="update-devicemanagementreportschedule"></a>更新 deviceManagementReportSchedule

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

更新 [deviceManagementReportSchedule](../resources/intune-reporting-devicemanagementreportschedule.md) 对象的属性。

## <a name="prerequisites"></a>先决条件
要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

|权限类型|权限（从最高特权到最低特权）|
|:---|:---|
|委派（工作或学校帐户）|Devicemanagementconfiguration.readwrite.all，Devicemanagementapps.readwrite.all，all，Devicemanagementmanageddevices.readwrite.all，All|
|委派（个人 Microsoft 帐户）|不支持。|
|应用程序|Devicemanagementconfiguration.readwrite.all，Devicemanagementapps.readwrite.all，all，Devicemanagementmanageddevices.readwrite.all，All|

## <a name="http-request"></a>HTTP 请求
<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /deviceManagement/reports/reportSchedules/{deviceManagementReportScheduleId}
```

## <a name="request-headers"></a>请求标头
|标头|值|
|:---|:---|
|Authorization|Bearer &lt;token&gt;。必需。|
|接受|application/json|

## <a name="request-body"></a>请求正文
在请求正文中，提供 [deviceManagementReportSchedule](../resources/intune-reporting-devicemanagementreportschedule.md) 对象的 JSON 表示形式。

下表显示创建 [deviceManagementReportSchedule](../resources/intune-reporting-devicemanagementreportschedule.md)时所需的属性。

|属性|类型|说明|
|:---|:---|:---|
|id|字符串|此实体的唯一标识符|
|reportScheduleName|字符串|计划的名称|
|subject|String|已传递的计划报告的主题|
|电子邮件|String 集合|计划报告传递到的电子邮件|
|recurrence|[deviceManagementScheduledReportRecurrence](../resources/intune-reporting-devicemanagementscheduledreportrecurrence.md)|计划报告传递的频率。 可取值为：`none`、`daily`、`weekly`、`monthly`。|
|startDateTime|DateTimeOffset|计划报告的开始交付时间|
|endDateTime|DateTimeOffset|计划报告的结束传递时间|
|userId|字符串|创建报表的用户的 Id|
|reportName|字符串|报告的名称|
|filter|字符串|在报表上应用的筛选器|
|select|String 集合|从报告中选择的列|
|By|String 集合|报表中的列的排序|
|format|[deviceManagementReportFileFormat](../resources/intune-reporting-devicemanagementreportfileformat.md)|计划报告的格式。 可取值为：`csv`、`pdf`。|



## <a name="response"></a>响应
如果成功，此方法 `200 OK` 在响应正文中返回响应代码和更新的 [deviceManagementReportSchedule](../resources/intune-reporting-devicemanagementreportschedule.md) 对象。

## <a name="example"></a>示例

### <a name="request"></a>请求
下面是一个请求示例。
``` http
PATCH https://graph.microsoft.com/beta/deviceManagement/reports/reportSchedules/{deviceManagementReportScheduleId}
Content-type: application/json
Content-length: 539

{
  "@odata.type": "#microsoft.graph.deviceManagementReportSchedule",
  "reportScheduleName": "Report Schedule Name value",
  "subject": "Subject value",
  "emails": [
    "Emails value"
  ],
  "recurrence": "daily",
  "startDateTime": "2016-12-31T23:58:46.7156189-08:00",
  "endDateTime": "2017-01-01T00:03:30.9241974-08:00",
  "userId": "User Id value",
  "reportName": "Report Name value",
  "filter": "Filter value",
  "select": [
    "Select value"
  ],
  "orderBy": [
    "Order By value"
  ],
  "format": "pdf"
}
```

### <a name="response"></a>响应
下面是一个响应示例。注意：为了简单起见，可能会将此处所示的响应对象截断。将从实际调用中返回所有属性。
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 588

{
  "@odata.type": "#microsoft.graph.deviceManagementReportSchedule",
  "id": "00bb9785-9785-00bb-8597-bb008597bb00",
  "reportScheduleName": "Report Schedule Name value",
  "subject": "Subject value",
  "emails": [
    "Emails value"
  ],
  "recurrence": "daily",
  "startDateTime": "2016-12-31T23:58:46.7156189-08:00",
  "endDateTime": "2017-01-01T00:03:30.9241974-08:00",
  "userId": "User Id value",
  "reportName": "Report Name value",
  "filter": "Filter value",
  "select": [
    "Select value"
  ],
  "orderBy": [
    "Order By value"
  ],
  "format": "pdf"
}
```




