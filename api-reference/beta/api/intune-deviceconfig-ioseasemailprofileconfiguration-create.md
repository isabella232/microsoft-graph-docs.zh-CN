---
title: 创建 iosEasEmailProfileConfiguration
description: 创建新的 iosEasEmailProfileConfiguration 对象。
author: tfitzmac
localization_priority: Normal
ms.prod: Intune
ms.openlocfilehash: 2ce4467b07bbebc79407e170813fe26fece86b5e
ms.sourcegitcommit: 20fef447f7e658a454a3887ea49746142c22e45c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "31801608"
---
# <a name="create-ioseasemailprofileconfiguration"></a><span data-ttu-id="3c714-103">创建 iosEasEmailProfileConfiguration</span><span class="sxs-lookup"><span data-stu-id="3c714-103">Create iosEasEmailProfileConfiguration</span></span>

> <span data-ttu-id="3c714-104">**重要说明:**/beta 版本下的 Microsoft Graph api 可能会发生更改;不支持生产使用。</span><span class="sxs-lookup"><span data-stu-id="3c714-104">**Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.</span></span>

> <span data-ttu-id="3c714-105">**注意:** 适用于 Intune 的 Microsoft Graph API 需要租户的[活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。</span><span class="sxs-lookup"><span data-stu-id="3c714-105">**Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.</span></span>

<span data-ttu-id="3c714-106">创建新的[iosEasEmailProfileConfiguration](../resources/intune-deviceconfig-ioseasemailprofileconfiguration.md)对象。</span><span class="sxs-lookup"><span data-stu-id="3c714-106">Create a new [iosEasEmailProfileConfiguration](../resources/intune-deviceconfig-ioseasemailprofileconfiguration.md) object.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c714-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="3c714-107">Prerequisites</span></span>
<span data-ttu-id="3c714-p101">要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。</span><span class="sxs-lookup"><span data-stu-id="3c714-p101">One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).</span></span>

|<span data-ttu-id="3c714-110">权限类型</span><span class="sxs-lookup"><span data-stu-id="3c714-110">Permission type</span></span>|<span data-ttu-id="3c714-111">权限（从最高特权到最低特权）</span><span class="sxs-lookup"><span data-stu-id="3c714-111">Permissions (from most to least privileged)</span></span>|
|:---|:---|
|<span data-ttu-id="3c714-112">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="3c714-112">Delegated (work or school account)</span></span>|<span data-ttu-id="3c714-113">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3c714-113">DeviceManagementConfiguration.ReadWrite.All</span></span>|
|<span data-ttu-id="3c714-114">委派（个人 Microsoft 帐户）</span><span class="sxs-lookup"><span data-stu-id="3c714-114">Delegated (personal Microsoft account)</span></span>|<span data-ttu-id="3c714-115">不支持。</span><span class="sxs-lookup"><span data-stu-id="3c714-115">Not supported.</span></span>|
|<span data-ttu-id="3c714-116">应用程序</span><span class="sxs-lookup"><span data-stu-id="3c714-116">Application</span></span>|<span data-ttu-id="3c714-117">不支持。</span><span class="sxs-lookup"><span data-stu-id="3c714-117">Not supported.</span></span>|

## <a name="http-request"></a><span data-ttu-id="3c714-118">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="3c714-118">HTTP Request</span></span>
<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /deviceManagement/deviceConfigurations
POST /deviceManagement/deviceConfigurations/{deviceConfigurationId}/microsoft.graph.windowsDomainJoinConfiguration/networkAccessConfigurations
```

## <a name="request-headers"></a><span data-ttu-id="3c714-119">请求标头</span><span class="sxs-lookup"><span data-stu-id="3c714-119">Request headers</span></span>
|<span data-ttu-id="3c714-120">标头</span><span class="sxs-lookup"><span data-stu-id="3c714-120">Header</span></span>|<span data-ttu-id="3c714-121">值</span><span class="sxs-lookup"><span data-stu-id="3c714-121">Value</span></span>|
|:---|:---|
|<span data-ttu-id="3c714-122">Authorization</span><span class="sxs-lookup"><span data-stu-id="3c714-122">Authorization</span></span>|<span data-ttu-id="3c714-123">Bearer &lt;token&gt;。必需。</span><span class="sxs-lookup"><span data-stu-id="3c714-123">Bearer &lt;token&gt; Required.</span></span>|
|<span data-ttu-id="3c714-124">接受</span><span class="sxs-lookup"><span data-stu-id="3c714-124">Accept</span></span>|<span data-ttu-id="3c714-125">application/json</span><span class="sxs-lookup"><span data-stu-id="3c714-125">application/json</span></span>|

## <a name="request-body"></a><span data-ttu-id="3c714-126">请求正文</span><span class="sxs-lookup"><span data-stu-id="3c714-126">Request body</span></span>
<span data-ttu-id="3c714-127">在请求正文中, 提供 iosEasEmailProfileConfiguration 对象的 JSON 表示形式。</span><span class="sxs-lookup"><span data-stu-id="3c714-127">In the request body, supply a JSON representation for the iosEasEmailProfileConfiguration object.</span></span>

<span data-ttu-id="3c714-128">下表显示创建 iosEasEmailProfileConfiguration 时所需的属性。</span><span class="sxs-lookup"><span data-stu-id="3c714-128">The following table shows the properties that are required when you create the iosEasEmailProfileConfiguration.</span></span>

|<span data-ttu-id="3c714-129">属性</span><span class="sxs-lookup"><span data-stu-id="3c714-129">Property</span></span>|<span data-ttu-id="3c714-130">类型</span><span class="sxs-lookup"><span data-stu-id="3c714-130">Type</span></span>|<span data-ttu-id="3c714-131">说明</span><span class="sxs-lookup"><span data-stu-id="3c714-131">Description</span></span>|
|:---|:---|:---|
|<span data-ttu-id="3c714-132">id</span><span class="sxs-lookup"><span data-stu-id="3c714-132">id</span></span>|<span data-ttu-id="3c714-133">String</span><span class="sxs-lookup"><span data-stu-id="3c714-133">String</span></span>|<span data-ttu-id="3c714-134">实体的键。</span><span class="sxs-lookup"><span data-stu-id="3c714-134">Key of the entity.</span></span> <span data-ttu-id="3c714-135">继承自 [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-135">Inherited from [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span></span>|
|<span data-ttu-id="3c714-136">lastModifiedDateTime</span><span class="sxs-lookup"><span data-stu-id="3c714-136">lastModifiedDateTime</span></span>|<span data-ttu-id="3c714-137">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3c714-137">DateTimeOffset</span></span>|<span data-ttu-id="3c714-138">上次修改对象的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="3c714-138">DateTime the object was last modified.</span></span> <span data-ttu-id="3c714-139">继承自 [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-139">Inherited from [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span></span>|
|<span data-ttu-id="3c714-140">roleScopeTagIds</span><span class="sxs-lookup"><span data-stu-id="3c714-140">roleScopeTagIds</span></span>|<span data-ttu-id="3c714-141">String 集合</span><span class="sxs-lookup"><span data-stu-id="3c714-141">String collection</span></span>|<span data-ttu-id="3c714-142">此实体实例的范围标记列表。</span><span class="sxs-lookup"><span data-stu-id="3c714-142">List of Scope Tags for this Entity instance.</span></span> <span data-ttu-id="3c714-143">继承自 [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-143">Inherited from [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span></span>|
|<span data-ttu-id="3c714-144">supportsScopeTags</span><span class="sxs-lookup"><span data-stu-id="3c714-144">supportsScopeTags</span></span>|<span data-ttu-id="3c714-145">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-145">Boolean</span></span>|<span data-ttu-id="3c714-146">指示基础设备配置是否支持作用域标记的分配。</span><span class="sxs-lookup"><span data-stu-id="3c714-146">Indicates whether or not the underlying Device Configuration supports the assignment of scope tags.</span></span> <span data-ttu-id="3c714-147">如果此值为 false, 则不允许分配给 ScopeTags 属性, 并且实体将对作用域用户不可见。</span><span class="sxs-lookup"><span data-stu-id="3c714-147">Assigning to the ScopeTags property is not allowed when this value is false and entities will not be visible to scoped users.</span></span> <span data-ttu-id="3c714-148">这适用于在 Silverlight 中创建的旧版策略, 可以通过在 Azure 门户中删除并重新创建策略来解决此事件。</span><span class="sxs-lookup"><span data-stu-id="3c714-148">This occurs for Legacy policies created in Silverlight and can be resolved by deleting and recreating the policy in the Azure Portal.</span></span> <span data-ttu-id="3c714-149">此属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="3c714-149">This property is read-only.</span></span> <span data-ttu-id="3c714-150">继承自 [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-150">Inherited from [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span></span>|
|<span data-ttu-id="3c714-151">createdDateTime</span><span class="sxs-lookup"><span data-stu-id="3c714-151">createdDateTime</span></span>|<span data-ttu-id="3c714-152">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3c714-152">DateTimeOffset</span></span>|<span data-ttu-id="3c714-153">创建对象的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="3c714-153">DateTime the object was created.</span></span> <span data-ttu-id="3c714-154">继承自 [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-154">Inherited from [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span></span>|
|<span data-ttu-id="3c714-155">description</span><span class="sxs-lookup"><span data-stu-id="3c714-155">description</span></span>|<span data-ttu-id="3c714-156">String</span><span class="sxs-lookup"><span data-stu-id="3c714-156">String</span></span>|<span data-ttu-id="3c714-157">管理员提供的设备配置的说明。</span><span class="sxs-lookup"><span data-stu-id="3c714-157">Admin provided description of the Device Configuration.</span></span> <span data-ttu-id="3c714-158">继承自 [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-158">Inherited from [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span></span>|
|<span data-ttu-id="3c714-159">displayName</span><span class="sxs-lookup"><span data-stu-id="3c714-159">displayName</span></span>|<span data-ttu-id="3c714-160">String</span><span class="sxs-lookup"><span data-stu-id="3c714-160">String</span></span>|<span data-ttu-id="3c714-161">管理员提供的设备配置的名称。</span><span class="sxs-lookup"><span data-stu-id="3c714-161">Admin provided name of the device configuration.</span></span> <span data-ttu-id="3c714-162">继承自 [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-162">Inherited from [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span></span>|
|<span data-ttu-id="3c714-163">version</span><span class="sxs-lookup"><span data-stu-id="3c714-163">version</span></span>|<span data-ttu-id="3c714-164">Int32</span><span class="sxs-lookup"><span data-stu-id="3c714-164">Int32</span></span>|<span data-ttu-id="3c714-165">设备配置的版本。</span><span class="sxs-lookup"><span data-stu-id="3c714-165">Version of the device configuration.</span></span> <span data-ttu-id="3c714-166">继承自 [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-166">Inherited from [deviceConfiguration](../resources/intune-deviceconfig-deviceconfiguration.md)</span></span>|
|<span data-ttu-id="3c714-167">usernameSource</span><span class="sxs-lookup"><span data-stu-id="3c714-167">usernameSource</span></span>|[<span data-ttu-id="3c714-168">userEmailSource</span><span class="sxs-lookup"><span data-stu-id="3c714-168">userEmailSource</span></span>](../resources/intune-deviceconfig-useremailsource.md)|<span data-ttu-id="3c714-169">在设备上安装之前, 从 AAD 中选取并插入到此配置文件中的 Username 属性。</span><span class="sxs-lookup"><span data-stu-id="3c714-169">Username attribute that is picked from AAD and injected into this profile before installing on the device.</span></span> <span data-ttu-id="3c714-170">继承自[easEmailProfileConfigurationBase](../resources/intune-deviceconfig-easemailprofileconfigurationbase.md)。</span><span class="sxs-lookup"><span data-stu-id="3c714-170">Inherited from [easEmailProfileConfigurationBase](../resources/intune-deviceconfig-easemailprofileconfigurationbase.md).</span></span> <span data-ttu-id="3c714-171">可取值为：`userPrincipalName`、`primarySmtpAddress`。</span><span class="sxs-lookup"><span data-stu-id="3c714-171">Possible values are: `userPrincipalName`, `primarySmtpAddress`.</span></span>|
|<span data-ttu-id="3c714-172">usernameAADSource</span><span class="sxs-lookup"><span data-stu-id="3c714-172">usernameAADSource</span></span>|[<span data-ttu-id="3c714-173">usernameSource</span><span class="sxs-lookup"><span data-stu-id="3c714-173">usernameSource</span></span>](../resources/intune-deviceconfig-usernamesource.md)|<span data-ttu-id="3c714-174">AAD 字段的名称, 将用于检索电子邮件配置文件的用户名。</span><span class="sxs-lookup"><span data-stu-id="3c714-174">Name of the AAD field, that will be used to retrieve UserName for email profile.</span></span> <span data-ttu-id="3c714-175">继承自[easEmailProfileConfigurationBase](../resources/intune-deviceconfig-easemailprofileconfigurationbase.md)。</span><span class="sxs-lookup"><span data-stu-id="3c714-175">Inherited from [easEmailProfileConfigurationBase](../resources/intune-deviceconfig-easemailprofileconfigurationbase.md).</span></span> <span data-ttu-id="3c714-176">可取值为：`userPrincipalName`、`primarySmtpAddress`、`samAccountName`。</span><span class="sxs-lookup"><span data-stu-id="3c714-176">Possible values are: `userPrincipalName`, `primarySmtpAddress`, `samAccountName`.</span></span>|
|<span data-ttu-id="3c714-177">userDomainNameSource</span><span class="sxs-lookup"><span data-stu-id="3c714-177">userDomainNameSource</span></span>|[<span data-ttu-id="3c714-178">domainNameSource</span><span class="sxs-lookup"><span data-stu-id="3c714-178">domainNameSource</span></span>](../resources/intune-deviceconfig-domainnamesource.md)|<span data-ttu-id="3c714-179">在设备上安装之前, 从 AAD 中选取并插入到此配置文件中的 UserDomainname 属性。</span><span class="sxs-lookup"><span data-stu-id="3c714-179">UserDomainname attribute that is picked from AAD and injected into this profile before installing on the device.</span></span> <span data-ttu-id="3c714-180">继承自[easEmailProfileConfigurationBase](../resources/intune-deviceconfig-easemailprofileconfigurationbase.md)。</span><span class="sxs-lookup"><span data-stu-id="3c714-180">Inherited from [easEmailProfileConfigurationBase](../resources/intune-deviceconfig-easemailprofileconfigurationbase.md).</span></span> <span data-ttu-id="3c714-181">可取值为：`fullDomainName`、`netBiosDomainName`。</span><span class="sxs-lookup"><span data-stu-id="3c714-181">Possible values are: `fullDomainName`, `netBiosDomainName`.</span></span>|
|<span data-ttu-id="3c714-182">customDomainName</span><span class="sxs-lookup"><span data-stu-id="3c714-182">customDomainName</span></span>|<span data-ttu-id="3c714-183">String</span><span class="sxs-lookup"><span data-stu-id="3c714-183">String</span></span>|<span data-ttu-id="3c714-184">在设备上安装之前生成电子邮件配置文件时使用的自定义域名值。</span><span class="sxs-lookup"><span data-stu-id="3c714-184">Custom domain name value used while generating an email profile before installing on the device.</span></span> <span data-ttu-id="3c714-185">继承自[easEmailProfileConfigurationBase](../resources/intune-deviceconfig-easemailprofileconfigurationbase.md)</span><span class="sxs-lookup"><span data-stu-id="3c714-185">Inherited from [easEmailProfileConfigurationBase](../resources/intune-deviceconfig-easemailprofileconfigurationbase.md)</span></span>|
|<span data-ttu-id="3c714-186">帐户</span><span class="sxs-lookup"><span data-stu-id="3c714-186">accountName</span></span>|<span data-ttu-id="3c714-187">String</span><span class="sxs-lookup"><span data-stu-id="3c714-187">String</span></span>|<span data-ttu-id="3c714-188">帐户名称。</span><span class="sxs-lookup"><span data-stu-id="3c714-188">Account name.</span></span>|
|<span data-ttu-id="3c714-189">authenticationMethod</span><span class="sxs-lookup"><span data-stu-id="3c714-189">authenticationMethod</span></span>|[<span data-ttu-id="3c714-190">easAuthenticationMethod</span><span class="sxs-lookup"><span data-stu-id="3c714-190">easAuthenticationMethod</span></span>](../resources/intune-deviceconfig-easauthenticationmethod.md)|<span data-ttu-id="3c714-191">此电子邮件配置文件的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="3c714-191">Authentication method for this Email profile.</span></span> <span data-ttu-id="3c714-192">可取值为：`usernameAndPassword`、`certificate`。</span><span class="sxs-lookup"><span data-stu-id="3c714-192">Possible values are: `usernameAndPassword`, `certificate`.</span></span>|
|<span data-ttu-id="3c714-193">blockMovingMessagesToOtherEmailAccounts</span><span class="sxs-lookup"><span data-stu-id="3c714-193">blockMovingMessagesToOtherEmailAccounts</span></span>|<span data-ttu-id="3c714-194">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-194">Boolean</span></span>|<span data-ttu-id="3c714-195">指示是否阻止将邮件移动到其他电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="3c714-195">Indicates whether or not to block moving messages to other email accounts.</span></span>|
|<span data-ttu-id="3c714-196">blockSendingEmailFromThirdPartyApps</span><span class="sxs-lookup"><span data-stu-id="3c714-196">blockSendingEmailFromThirdPartyApps</span></span>|<span data-ttu-id="3c714-197">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-197">Boolean</span></span>|<span data-ttu-id="3c714-198">指示是否阻止来自第三方应用的发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3c714-198">Indicates whether or not to block sending email from third party apps.</span></span>|
|<span data-ttu-id="3c714-199">blockSyncingRecentlyUsedEmailAddresses</span><span class="sxs-lookup"><span data-stu-id="3c714-199">blockSyncingRecentlyUsedEmailAddresses</span></span>|<span data-ttu-id="3c714-200">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-200">Boolean</span></span>|<span data-ttu-id="3c714-201">指示是否阻止同步最近使用的电子邮件地址, 例如, 撰写新电子邮件时。</span><span class="sxs-lookup"><span data-stu-id="3c714-201">Indicates whether or not to block syncing recently used email addresses, for instance - when composing new email.</span></span>|
|<span data-ttu-id="3c714-202">durationOfEmailToSync</span><span class="sxs-lookup"><span data-stu-id="3c714-202">durationOfEmailToSync</span></span>|[<span data-ttu-id="3c714-203">emailSyncDuration</span><span class="sxs-lookup"><span data-stu-id="3c714-203">emailSyncDuration</span></span>](../resources/intune-deviceconfig-emailsyncduration.md)|<span data-ttu-id="3c714-204">电子邮件的持续时间应同步回。</span><span class="sxs-lookup"><span data-stu-id="3c714-204">Duration of time email should be synced back to.</span></span> <span data-ttu-id="3c714-205">.</span><span class="sxs-lookup"><span data-stu-id="3c714-205"></span></span> <span data-ttu-id="3c714-206">可取值为：`userDefined`、`oneDay`、`threeDays`、`oneWeek`、`twoWeeks`、`oneMonth` 或 `unlimited`。</span><span class="sxs-lookup"><span data-stu-id="3c714-206">Possible values are: `userDefined`, `oneDay`, `threeDays`, `oneWeek`, `twoWeeks`, `oneMonth`, `unlimited`.</span></span>|
|<span data-ttu-id="3c714-207">emailAddressSource</span><span class="sxs-lookup"><span data-stu-id="3c714-207">emailAddressSource</span></span>|[<span data-ttu-id="3c714-208">userEmailSource</span><span class="sxs-lookup"><span data-stu-id="3c714-208">userEmailSource</span></span>](../resources/intune-deviceconfig-useremailsource.md)|<span data-ttu-id="3c714-209">在设备上安装之前, 从 AAD 中选出并插入到此配置文件中的电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="3c714-209">Email attribute that is picked from AAD and injected into this profile before installing on the device.</span></span> <span data-ttu-id="3c714-210">可取值为：`userPrincipalName`、`primarySmtpAddress`。</span><span class="sxs-lookup"><span data-stu-id="3c714-210">Possible values are: `userPrincipalName`, `primarySmtpAddress`.</span></span>|
|<span data-ttu-id="3c714-211">hostName</span><span class="sxs-lookup"><span data-stu-id="3c714-211">hostName</span></span>|<span data-ttu-id="3c714-212">String</span><span class="sxs-lookup"><span data-stu-id="3c714-212">String</span></span>|<span data-ttu-id="3c714-213">本机邮件应用程序连接到的 Exchange 位置 (URL)。</span><span class="sxs-lookup"><span data-stu-id="3c714-213">Exchange location that (URL) that the native mail app connects to.</span></span>|
|<span data-ttu-id="3c714-214">requireSmime</span><span class="sxs-lookup"><span data-stu-id="3c714-214">requireSmime</span></span>|<span data-ttu-id="3c714-215">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-215">Boolean</span></span>|<span data-ttu-id="3c714-216">指示是否使用 S/MIME 证书。</span><span class="sxs-lookup"><span data-stu-id="3c714-216">Indicates whether or not to use S/MIME certificate.</span></span>|
|<span data-ttu-id="3c714-217">smimeEnablePerMessageSwitch</span><span class="sxs-lookup"><span data-stu-id="3c714-217">smimeEnablePerMessageSwitch</span></span>|<span data-ttu-id="3c714-218">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-218">Boolean</span></span>|<span data-ttu-id="3c714-219">指示是否允许未加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3c714-219">Indicates whether or not to allow unencrypted emails.</span></span>|
|<span data-ttu-id="3c714-220">smimeEncryptByDefaultEnabled</span><span class="sxs-lookup"><span data-stu-id="3c714-220">smimeEncryptByDefaultEnabled</span></span>|<span data-ttu-id="3c714-221">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-221">Boolean</span></span>|<span data-ttu-id="3c714-222">如果设置为 "true S/MIME 加密", 则默认为启用。</span><span class="sxs-lookup"><span data-stu-id="3c714-222">If set to true S/MIME encryption is enabled by default.</span></span>|
|<span data-ttu-id="3c714-223">smimeSigningEnabled</span><span class="sxs-lookup"><span data-stu-id="3c714-223">smimeSigningEnabled</span></span>|<span data-ttu-id="3c714-224">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-224">Boolean</span></span>|<span data-ttu-id="3c714-225">如果为此帐户启用了设置为 true S/MIME 签名</span><span class="sxs-lookup"><span data-stu-id="3c714-225">If set to true S/MIME signing is enabled for this account</span></span>|
|<span data-ttu-id="3c714-226">smimeSigningUserOverrideEnabled</span><span class="sxs-lookup"><span data-stu-id="3c714-226">smimeSigningUserOverrideEnabled</span></span>|<span data-ttu-id="3c714-227">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-227">Boolean</span></span>|<span data-ttu-id="3c714-228">如果设置为 true, 则用户可以打开或关闭 S/MIME 签名。</span><span class="sxs-lookup"><span data-stu-id="3c714-228">If set to true, the user can toggle S/MIME signing on or off.</span></span>|
|<span data-ttu-id="3c714-229">smimeEncryptByDefaultUserOverrideEnabled</span><span class="sxs-lookup"><span data-stu-id="3c714-229">smimeEncryptByDefaultUserOverrideEnabled</span></span>|<span data-ttu-id="3c714-230">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-230">Boolean</span></span>|<span data-ttu-id="3c714-231">如果设置为 true, 则用户可以默认切换加密设置。</span><span class="sxs-lookup"><span data-stu-id="3c714-231">If set to true, the user can toggle the encryption by default setting.</span></span>|
|<span data-ttu-id="3c714-232">smimeSigningCertificateUserOverrideEnabled</span><span class="sxs-lookup"><span data-stu-id="3c714-232">smimeSigningCertificateUserOverrideEnabled</span></span>|<span data-ttu-id="3c714-233">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-233">Boolean</span></span>|<span data-ttu-id="3c714-234">如果设置为 true, 则用户可以选择签名标识。</span><span class="sxs-lookup"><span data-stu-id="3c714-234">If set to true, the user can select the signing identity.</span></span>|
|<span data-ttu-id="3c714-235">smimeEncryptionCertificateUserOverrideEnabled</span><span class="sxs-lookup"><span data-stu-id="3c714-235">smimeEncryptionCertificateUserOverrideEnabled</span></span>|<span data-ttu-id="3c714-236">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-236">Boolean</span></span>|<span data-ttu-id="3c714-237">如果设置为 true, 则用户可以选择 S/MIME 加密标识。</span><span class="sxs-lookup"><span data-stu-id="3c714-237">If set to true the user can select the S/MIME encryption identity.</span></span> |
|<span data-ttu-id="3c714-238">requireSsl</span><span class="sxs-lookup"><span data-stu-id="3c714-238">requireSsl</span></span>|<span data-ttu-id="3c714-239">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-239">Boolean</span></span>|<span data-ttu-id="3c714-240">指示是否使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="3c714-240">Indicates whether or not to use SSL.</span></span>|
|<span data-ttu-id="3c714-241">useOAuth</span><span class="sxs-lookup"><span data-stu-id="3c714-241">useOAuth</span></span>|<span data-ttu-id="3c714-242">布尔值</span><span class="sxs-lookup"><span data-stu-id="3c714-242">Boolean</span></span>|<span data-ttu-id="3c714-243">指定连接是否应使用 OAuth 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c714-243">Specifies whether the connection should use OAuth for authentication.</span></span>|



## <a name="response"></a><span data-ttu-id="3c714-244">响应</span><span class="sxs-lookup"><span data-stu-id="3c714-244">Response</span></span>
<span data-ttu-id="3c714-245">如果成功, 此方法在响应`201 Created`正文中返回响应代码和[iosEasEmailProfileConfiguration](../resources/intune-deviceconfig-ioseasemailprofileconfiguration.md)对象。</span><span class="sxs-lookup"><span data-stu-id="3c714-245">If successful, this method returns a `201 Created` response code and a [iosEasEmailProfileConfiguration](../resources/intune-deviceconfig-ioseasemailprofileconfiguration.md) object in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="3c714-246">示例</span><span class="sxs-lookup"><span data-stu-id="3c714-246">Example</span></span>

### <a name="request"></a><span data-ttu-id="3c714-247">请求</span><span class="sxs-lookup"><span data-stu-id="3c714-247">Request</span></span>
<span data-ttu-id="3c714-248">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="3c714-248">Here is an example of the request.</span></span>
``` http
POST https://graph.microsoft.com/beta/deviceManagement/deviceConfigurations
Content-type: application/json
Content-length: 1193

{
  "@odata.type": "#microsoft.graph.iosEasEmailProfileConfiguration",
  "roleScopeTagIds": [
    "Role Scope Tag Ids value"
  ],
  "supportsScopeTags": true,
  "description": "Description value",
  "displayName": "Display Name value",
  "version": 7,
  "usernameSource": "primarySmtpAddress",
  "usernameAADSource": "primarySmtpAddress",
  "userDomainNameSource": "netBiosDomainName",
  "customDomainName": "Custom Domain Name value",
  "accountName": "Account Name value",
  "authenticationMethod": "certificate",
  "blockMovingMessagesToOtherEmailAccounts": true,
  "blockSendingEmailFromThirdPartyApps": true,
  "blockSyncingRecentlyUsedEmailAddresses": true,
  "durationOfEmailToSync": "oneDay",
  "emailAddressSource": "primarySmtpAddress",
  "hostName": "Host Name value",
  "requireSmime": true,
  "smimeEnablePerMessageSwitch": true,
  "smimeEncryptByDefaultEnabled": true,
  "smimeSigningEnabled": true,
  "smimeSigningUserOverrideEnabled": true,
  "smimeEncryptByDefaultUserOverrideEnabled": true,
  "smimeSigningCertificateUserOverrideEnabled": true,
  "smimeEncryptionCertificateUserOverrideEnabled": true,
  "requireSsl": true,
  "useOAuth": true
}
```

### <a name="response"></a><span data-ttu-id="3c714-249">响应</span><span class="sxs-lookup"><span data-stu-id="3c714-249">Response</span></span>
<span data-ttu-id="3c714-p117">下面是一个响应示例。注意：为了简单起见，可能会将此处所示的响应对象截断。将从实际调用中返回所有属性。</span><span class="sxs-lookup"><span data-stu-id="3c714-p117">Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.</span></span>
``` http
HTTP/1.1 201 Created
Content-Type: application/json
Content-Length: 1365

{
  "@odata.type": "#microsoft.graph.iosEasEmailProfileConfiguration",
  "id": "e03086da-86da-e030-da86-30e0da8630e0",
  "lastModifiedDateTime": "2017-01-01T00:00:35.1329464-08:00",
  "roleScopeTagIds": [
    "Role Scope Tag Ids value"
  ],
  "supportsScopeTags": true,
  "createdDateTime": "2017-01-01T00:02:43.5775965-08:00",
  "description": "Description value",
  "displayName": "Display Name value",
  "version": 7,
  "usernameSource": "primarySmtpAddress",
  "usernameAADSource": "primarySmtpAddress",
  "userDomainNameSource": "netBiosDomainName",
  "customDomainName": "Custom Domain Name value",
  "accountName": "Account Name value",
  "authenticationMethod": "certificate",
  "blockMovingMessagesToOtherEmailAccounts": true,
  "blockSendingEmailFromThirdPartyApps": true,
  "blockSyncingRecentlyUsedEmailAddresses": true,
  "durationOfEmailToSync": "oneDay",
  "emailAddressSource": "primarySmtpAddress",
  "hostName": "Host Name value",
  "requireSmime": true,
  "smimeEnablePerMessageSwitch": true,
  "smimeEncryptByDefaultEnabled": true,
  "smimeSigningEnabled": true,
  "smimeSigningUserOverrideEnabled": true,
  "smimeEncryptByDefaultUserOverrideEnabled": true,
  "smimeSigningCertificateUserOverrideEnabled": true,
  "smimeEncryptionCertificateUserOverrideEnabled": true,
  "requireSsl": true,
  "useOAuth": true
}
```





