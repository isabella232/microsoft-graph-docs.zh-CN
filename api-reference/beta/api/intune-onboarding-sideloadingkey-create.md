---
title: 创建 sideLoadingKey
description: 创建新的 sideLoadingKey 对象。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: apiPageType
ms.openlocfilehash: 9cdde6b87f573414860abab77d82c17216c09170
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49276894"
---
# <a name="create-sideloadingkey"></a>创建 sideLoadingKey

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

创建新的 [sideLoadingKey](../resources/intune-onboarding-sideloadingkey.md) 对象。

## <a name="prerequisites"></a>先决条件
要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

|权限类型|权限（从最高特权到最低特权）|
|:---|:---|
|委派（工作或学校帐户）|DeviceManagementServiceConfig.ReadWrite.All|
|委派（个人 Microsoft 帐户）|不支持。|
|应用程序|DeviceManagementServiceConfig.ReadWrite.All|

## <a name="http-request"></a>HTTP 请求
<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /deviceAppManagement/sideLoadingKeys
```

## <a name="request-headers"></a>请求标头
|标头|值|
|:---|:---|
|Authorization|Bearer &lt;token&gt;。必需。|
|接受|application/json|

## <a name="request-body"></a>请求正文
在请求正文中，提供 sideLoadingKey 对象的 JSON 表示形式。

下表显示创建 sideLoadingKey 时所需的属性。

|属性|类型|说明|
|:---|:---|:---|
|id|字符串|侧加载密钥唯一 Id。|
|value|String|侧加载密钥值，它是一个5x5 值，由 hiphens 分隔。|
|displayName|字符串|向 It 专业管理员显示的侧加载密钥名称。|
|description|字符串|向 It 专业管理员显示的侧加载密钥说明。|
|totalActivation|Int32|向 It 专业管理员显示的端加载密钥总激活数。|
|lastUpdatedDateTime|字符串|向 It 专业管理员显示的侧加载密钥上次更新日期。|



## <a name="response"></a>响应
如果成功，此方法 `201 Created` 在响应正文中返回响应代码和 [sideLoadingKey](../resources/intune-onboarding-sideloadingkey.md) 对象。

## <a name="example"></a>示例

### <a name="request"></a>请求
下面是一个请求示例。
``` http
POST https://graph.microsoft.com/beta/deviceAppManagement/sideLoadingKeys
Content-type: application/json
Content-length: 246

{
  "@odata.type": "#microsoft.graph.sideLoadingKey",
  "value": "Value value",
  "displayName": "Display Name value",
  "description": "Description value",
  "totalActivation": 15,
  "lastUpdatedDateTime": "Last Updated Date Time value"
}
```

### <a name="response"></a>响应
下面是一个响应示例。注意：为了简单起见，可能会将此处所示的响应对象截断。将从实际调用中返回所有属性。
``` http
HTTP/1.1 201 Created
Content-Type: application/json
Content-Length: 295

{
  "@odata.type": "#microsoft.graph.sideLoadingKey",
  "id": "21c4a3ff-a3ff-21c4-ffa3-c421ffa3c421",
  "value": "Value value",
  "displayName": "Display Name value",
  "description": "Description value",
  "totalActivation": 15,
  "lastUpdatedDateTime": "Last Updated Date Time value"
}
```




