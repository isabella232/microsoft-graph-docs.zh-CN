---
title: 更新 importedWindowsAutopilotDeviceIdentityUpload
description: 更新 importedWindowsAutopilotDeviceIdentityUpload 对象的属性。
author: rolyon
localization_priority: Normal
ms.prod: Intune
doc_type: apiPageType
ms.openlocfilehash: 867561d9c361cbc725b6223d08d51002680d82f3
ms.sourcegitcommit: 2c62457e57467b8d50f21b255b553106a9a5d8d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "35985561"
---
# <a name="update-importedwindowsautopilotdeviceidentityupload"></a><span data-ttu-id="f1fae-103">更新 importedWindowsAutopilotDeviceIdentityUpload</span><span class="sxs-lookup"><span data-stu-id="f1fae-103">Update importedWindowsAutopilotDeviceIdentityUpload</span></span>

> <span data-ttu-id="f1fae-104">**重要说明:**/Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。</span><span class="sxs-lookup"><span data-stu-id="f1fae-104">**Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.</span></span>

> <span data-ttu-id="f1fae-105">**注意:** 适用于 Intune 的 Microsoft Graph API 需要租户的[活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。</span><span class="sxs-lookup"><span data-stu-id="f1fae-105">**Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.</span></span>

<span data-ttu-id="f1fae-106">更新[importedWindowsAutopilotDeviceIdentityUpload](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityupload.md)对象的属性。</span><span class="sxs-lookup"><span data-stu-id="f1fae-106">Update the properties of a [importedWindowsAutopilotDeviceIdentityUpload](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityupload.md) object.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1fae-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="f1fae-107">Prerequisites</span></span>
<span data-ttu-id="f1fae-p101">要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。</span><span class="sxs-lookup"><span data-stu-id="f1fae-p101">One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).</span></span>

|<span data-ttu-id="f1fae-110">权限类型</span><span class="sxs-lookup"><span data-stu-id="f1fae-110">Permission type</span></span>|<span data-ttu-id="f1fae-111">权限（从最高特权到最低特权）</span><span class="sxs-lookup"><span data-stu-id="f1fae-111">Permissions (from most to least privileged)</span></span>|
|:---|:---|
|<span data-ttu-id="f1fae-112">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="f1fae-112">Delegated (work or school account)</span></span>|<span data-ttu-id="f1fae-113">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f1fae-113">DeviceManagementServiceConfig.ReadWrite.All</span></span>|
|<span data-ttu-id="f1fae-114">委派（个人 Microsoft 帐户）</span><span class="sxs-lookup"><span data-stu-id="f1fae-114">Delegated (personal Microsoft account)</span></span>|<span data-ttu-id="f1fae-115">不支持。</span><span class="sxs-lookup"><span data-stu-id="f1fae-115">Not supported.</span></span>|
|<span data-ttu-id="f1fae-116">应用程序</span><span class="sxs-lookup"><span data-stu-id="f1fae-116">Application</span></span>|<span data-ttu-id="f1fae-117">不支持。</span><span class="sxs-lookup"><span data-stu-id="f1fae-117">Not supported.</span></span>|

## <a name="http-request"></a><span data-ttu-id="f1fae-118">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="f1fae-118">HTTP Request</span></span>
<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /deviceManagement/importedWindowsAutopilotDeviceIdentityUploads/{importedWindowsAutopilotDeviceIdentityUploadId}
```

## <a name="request-headers"></a><span data-ttu-id="f1fae-119">请求标头</span><span class="sxs-lookup"><span data-stu-id="f1fae-119">Request headers</span></span>
|<span data-ttu-id="f1fae-120">标头</span><span class="sxs-lookup"><span data-stu-id="f1fae-120">Header</span></span>|<span data-ttu-id="f1fae-121">值</span><span class="sxs-lookup"><span data-stu-id="f1fae-121">Value</span></span>|
|:---|:---|
|<span data-ttu-id="f1fae-122">Authorization</span><span class="sxs-lookup"><span data-stu-id="f1fae-122">Authorization</span></span>|<span data-ttu-id="f1fae-123">Bearer &lt;token&gt;。必需。</span><span class="sxs-lookup"><span data-stu-id="f1fae-123">Bearer &lt;token&gt; Required.</span></span>|
|<span data-ttu-id="f1fae-124">接受</span><span class="sxs-lookup"><span data-stu-id="f1fae-124">Accept</span></span>|<span data-ttu-id="f1fae-125">application/json</span><span class="sxs-lookup"><span data-stu-id="f1fae-125">application/json</span></span>|

## <a name="request-body"></a><span data-ttu-id="f1fae-126">请求正文</span><span class="sxs-lookup"><span data-stu-id="f1fae-126">Request body</span></span>
<span data-ttu-id="f1fae-127">在请求正文中, 提供[importedWindowsAutopilotDeviceIdentityUpload](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityupload.md)对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="f1fae-127">In the request body, supply a JSON representation for the [importedWindowsAutopilotDeviceIdentityUpload](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityupload.md) object.</span></span>

<span data-ttu-id="f1fae-128">下表显示创建[importedWindowsAutopilotDeviceIdentityUpload](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityupload.md)时所需的属性。</span><span class="sxs-lookup"><span data-stu-id="f1fae-128">The following table shows the properties that are required when you create the [importedWindowsAutopilotDeviceIdentityUpload](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityupload.md).</span></span>

|<span data-ttu-id="f1fae-129">属性</span><span class="sxs-lookup"><span data-stu-id="f1fae-129">Property</span></span>|<span data-ttu-id="f1fae-130">类型</span><span class="sxs-lookup"><span data-stu-id="f1fae-130">Type</span></span>|<span data-ttu-id="f1fae-131">说明</span><span class="sxs-lookup"><span data-stu-id="f1fae-131">Description</span></span>|
|:---|:---|:---|
|<span data-ttu-id="f1fae-132">id</span><span class="sxs-lookup"><span data-stu-id="f1fae-132">id</span></span>|<span data-ttu-id="f1fae-133">String</span><span class="sxs-lookup"><span data-stu-id="f1fae-133">String</span></span>|<span data-ttu-id="f1fae-134">对象的 GUID</span><span class="sxs-lookup"><span data-stu-id="f1fae-134">The GUID for the object</span></span>|
|<span data-ttu-id="f1fae-135">createdDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="f1fae-135">createdDateTimeUtc</span></span>|<span data-ttu-id="f1fae-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f1fae-136">DateTimeOffset</span></span>|<span data-ttu-id="f1fae-137">创建实体时的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="f1fae-137">DateTime when the entity is created.</span></span>|
|<span data-ttu-id="f1fae-138">status</span><span class="sxs-lookup"><span data-stu-id="f1fae-138">status</span></span>|[<span data-ttu-id="f1fae-139">importedWindowsAutopilotDeviceIdentityUploadStatus</span><span class="sxs-lookup"><span data-stu-id="f1fae-139">importedWindowsAutopilotDeviceIdentityUploadStatus</span></span>](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityuploadstatus.md)|<span data-ttu-id="f1fae-140">上载状态。</span><span class="sxs-lookup"><span data-stu-id="f1fae-140">Upload status.</span></span> <span data-ttu-id="f1fae-141">可取值为：`noUpload`、`pending`、`complete`、`error`。</span><span class="sxs-lookup"><span data-stu-id="f1fae-141">Possible values are: `noUpload`, `pending`, `complete`, `error`.</span></span>|



## <a name="response"></a><span data-ttu-id="f1fae-142">响应</span><span class="sxs-lookup"><span data-stu-id="f1fae-142">Response</span></span>
<span data-ttu-id="f1fae-143">如果成功, 此方法在响应`200 OK`正文中返回响应代码和更新的[importedWindowsAutopilotDeviceIdentityUpload](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityupload.md)对象。</span><span class="sxs-lookup"><span data-stu-id="f1fae-143">If successful, this method returns a `200 OK` response code and an updated [importedWindowsAutopilotDeviceIdentityUpload](../resources/intune-enrollment-importedwindowsautopilotdeviceidentityupload.md) object in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="f1fae-144">示例</span><span class="sxs-lookup"><span data-stu-id="f1fae-144">Example</span></span>

### <a name="request"></a><span data-ttu-id="f1fae-145">请求</span><span class="sxs-lookup"><span data-stu-id="f1fae-145">Request</span></span>
<span data-ttu-id="f1fae-146">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="f1fae-146">Here is an example of the request.</span></span>
``` http
PATCH https://graph.microsoft.com/beta/deviceManagement/importedWindowsAutopilotDeviceIdentityUploads/{importedWindowsAutopilotDeviceIdentityUploadId}
Content-type: application/json
Content-length: 172

{
  "@odata.type": "#microsoft.graph.importedWindowsAutopilotDeviceIdentityUpload",
  "createdDateTimeUtc": "2016-12-31T23:59:45.8788427-08:00",
  "status": "pending"
}
```

### <a name="response"></a><span data-ttu-id="f1fae-147">响应</span><span class="sxs-lookup"><span data-stu-id="f1fae-147">Response</span></span>
<span data-ttu-id="f1fae-p103">下面是一个响应示例。注意：为了简单起见，可能会将此处所示的响应对象截断。将从实际调用中返回所有属性。</span><span class="sxs-lookup"><span data-stu-id="f1fae-p103">Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.</span></span>
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 221

{
  "@odata.type": "#microsoft.graph.importedWindowsAutopilotDeviceIdentityUpload",
  "id": "8d639524-9524-8d63-2495-638d2495638d",
  "createdDateTimeUtc": "2016-12-31T23:59:45.8788427-08:00",
  "status": "pending"
}
```




