---
title: windowsWifiEnterpriseEAPConfiguration 资源类型
description: 此实体提供由 Wifi CSP 公开的已声明方法、属性和关系的说明。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: cc94b4b05c38d3939c83ecef729acd677aab8522
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49226634"
---
# <a name="windowswifienterpriseeapconfiguration-resource-type"></a>windowsWifiEnterpriseEAPConfiguration 资源类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

此实体提供由 Wifi CSP 公开的已声明方法、属性和关系的说明。


继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)

## <a name="methods"></a>方法
|方法|返回类型|说明|
|:---|:---|:---|
|[列出 windowsWifiEnterpriseEAPConfigurations](../api/intune-deviceconfig-windowswifienterpriseeapconfiguration-list.md)|[windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md) 集合|列出 [windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md) 对象的属性和关系。|
|[获取 windowsWifiEnterpriseEAPConfiguration](../api/intune-deviceconfig-windowswifienterpriseeapconfiguration-get.md)|[windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md)|读取 [windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md) 对象的属性和关系。|
|[创建 windowsWifiEnterpriseEAPConfiguration](../api/intune-deviceconfig-windowswifienterpriseeapconfiguration-create.md)|[windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md)|创建新的 [windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md) 对象。|
|[删除 windowsWifiEnterpriseEAPConfiguration](../api/intune-deviceconfig-windowswifienterpriseeapconfiguration-delete.md)|无|删除 [windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md)。|
|[更新 windowsWifiEnterpriseEAPConfiguration](../api/intune-deviceconfig-windowswifienterpriseeapconfiguration-update.md)|[windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md)|更新 [windowsWifiEnterpriseEAPConfiguration](../resources/intune-deviceconfig-windowswifienterpriseeapconfiguration.md) 对象的属性。|

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|id|String|实体的键。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|lastModifiedDateTime|DateTimeOffset|上次修改对象的日期/时间。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|roleScopeTagIds|String 集合|此实体实例的范围标记列表。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|supportsScopeTags|Boolean|指示基础设备配置是否支持作用域标记的分配。 如果此值为 false，则不允许分配给 ScopeTags 属性，并且实体将对作用域用户不可见。 这适用于在 Silverlight 中创建的旧版策略，可以通过在 Azure 门户中删除并重新创建策略来解决此事件。 此属性是只读的。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|deviceManagementApplicabilityRuleOsEdition|[deviceManagementApplicabilityRuleOsEdition](../resources/intune-deviceconfig-devicemanagementapplicabilityruleosedition.md)|适用于此策略的操作系统版本。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|deviceManagementApplicabilityRuleOsVersion|[deviceManagementApplicabilityRuleOsVersion](../resources/intune-deviceconfig-devicemanagementapplicabilityruleosversion.md)|此策略的操作系统版本适用性规则。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|deviceManagementApplicabilityRuleDeviceMode|[deviceManagementApplicabilityRuleDeviceMode](../resources/intune-deviceconfig-devicemanagementapplicabilityruledevicemode.md)|此策略的设备模式适用性规则。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|createdDateTime|DateTimeOffset|创建对象的日期/时间。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|description|String|管理员提供的设备配置的说明。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|displayName|String|管理员提供的设备配置的名称。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|version|Int32|设备配置的版本。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|preSharedKey|String|这是 WPA 个人 Wi-Fi 网络的预共享密钥。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|wifiSecurityType|[wiFiSecurityType](../resources/intune-deviceconfig-wifisecuritytype.md)|指定 Wifi 安全类型。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)。 可取值为：`open`、`wpaPersonal`、`wpaEnterprise`、`wep`、`wpa2Personal`、`wpa2Enterprise`。|
|meteredConnectionLimit|[meteredConnectionLimitType](../resources/intune-deviceconfig-meteredconnectionlimittype.md)|为 wifi 连接指定按流量计费的连接限制类型。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)。 可取值为：`unrestricted`、`fixed`、`variable`。|
|ssid|String|指定 wifi 连接的 SSID。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|networkName|String|指定网络配置名称。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|connectAutomatically|Boolean|指定是否在范围内自动连接 wifi 连接。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|connectToPreferredNetwork|Boolean|指定 wifi 连接是否应连接到更多的首选网络（如果已连接到此连接的话）。  要求 ConnectAutomatically 为 true。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|connectWhenNetworkNameIsHidden|Boolean|指定是否应自动连接 wifi 连接，即使 SSID 未进行广播也是如此。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|proxySetting|[wiFiProxySetting](../resources/intune-deviceconfig-wifiproxysetting.md)|指定从 [WindowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)继承的 Wi-Fi 配置的代理设置。 可取值为：`none`、`manual`、`automatic`。|
|proxyManualAddress|String|指定代理服务器的 IP 地址。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|proxyManualPort|Int32|指定代理服务器的端口。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|proxyAutomaticConfigurationUrl|String|指定代理服务器配置脚本的 URL。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|forceFIPSCompliance|Boolean|指定是否强制进行 FIPS 合规性。 继承自 [windowsWifiConfiguration](../resources/intune-deviceconfig-windowswificonfiguration.md)|
|networkSingleSignOn|[networkSingleSignOnType](../resources/intune-deviceconfig-networksinglesignontype.md)|指定网络单一登录类型。 可取值为：`disabled`、`prelogon`、`postlogon`。|
|maximumAuthenticationTimeoutInSeconds|Int32|以秒为单位指定最大身份验证超时 () 。  有效范围：1-120|
|userBasedVirtualLan|Boolean|指定是否根据用户的凭据更改设备使用的虚拟 LAN。 将 NetworkSingleSignOnType 设置为 Disabled 时无法使用。|
|promptForAdditionalAuthenticationCredentials|Boolean|指定 wifi 连接是否应提示额外的身份验证凭据。|
|enablePairwiseMasterKeyCaching|Boolean|指定 wifi 连接是否应启用成对主密钥缓存。|
|maximumPairwiseMasterKeyCacheTimeInMinutes|Int32|指定最大成对主密钥缓存时间 (以分钟) 为单位）。  有效范围：5-1440|
|maximumNumberOfPairwiseMasterKeysInCache|Int32|指定缓存中成对主密钥的最大数量。  有效范围：1-255|
|enablePreAuthentication|Boolean|指定是否应启用预先身份验证。|
|maximumPreAuthenticationAttempts|Int32|指定最大预先身份验证尝试次数。  有效范围：1-16|
|eapType|[eapType](../resources/intune-deviceconfig-eaptype.md)|可扩展的身份验证协议 (EAP) 。 指示 Wi-Fi 终结点 (路由器) 上的 EAP 协议集的类型。 可取值为：`eapTls`、`leap`、`eapSim`、`eapTtls`、`peap`、`eapFast`。|
|trustedServerCertificateNames|String 集合|指定受信任的服务器证书名称。|
|authenticationMethod|[wiFiAuthenticationMethod](../resources/intune-deviceconfig-wifiauthenticationmethod.md)|指定身份验证方法。 可取值为：`certificate`、`usernameAndPassword`、`derivedCredential`。|
|innerAuthenticationProtocolForEAPTTLS|[nonEapAuthenticationMethodForEapTtlsType](../resources/intune-deviceconfig-noneapauthenticationmethodforeapttlstype.md)|为 EAP TTLS 指定内部身份验证协议。 可取值为：`unencryptedPassword`、`challengeHandshakeAuthenticationProtocol`、`microsoftChap`、`microsoftChapVersionTwo`。|
|outerIdentityPrivacyTemporaryValue|String|指定在使用 EAP TTLS 或 PEAP 时用于替换隐私的用户名的字符串。|
|requireCryptographicBinding|Boolean|指定在选择 EAP 类型作为 PEAP 时是否启用加密绑定。|
|performServerValidation|Boolean|通过在选择 EAP 类型作为 PEAP 时验证证书来指定是否启用对服务器标识的验证。|
|disableUserPromptForServerValidation|Boolean|当选择 EAP 类型作为 PEAP 时，指定是否阻止提示用户为受信任的证书颁发机构授权新服务器。|
|authenticationPeriodInSeconds|Int32|指定客户端在失败前的身份验证尝试之后等待的秒数。 有效范围为1-3600。|
|authenticationRetryDelayPeriodInSeconds|Int32|指定失败的身份验证和下一次身份验证尝试之间的秒数。 有效范围为1-3600。|
|eapolStartPeriodInSeconds|Int32|指定通过 LAN) 启动邮件发送 EAPOL (可扩展身份验证协议之前要等待的秒数。 有效范围为1-3600。|
|maximumEAPOLStartMessages|Int32|指定在返回失败之前要发送的 EAPOL (可扩展身份验证协议的最大数量，) 启动要发送的消息。 有效范围为1-100。|
|maximumAuthenticationFailures|Int32|指定允许的一组凭据的最大身份验证失败次数。 有效范围为1-100。|
|cacheCredentials|Boolean|指定是否在设备上缓存用户凭据，以便用户在每次连接时无需继续输入它们。|
|authenticationType|[wifiAuthenticationType](../resources/intune-deviceconfig-wifiauthenticationtype.md)|指定是对用户、设备还是使用来宾身份验证 (无) 进行身份验证。 如果使用的是证书身份验证，请确保证书类型与身份验证类型相匹配。 可取值为：`none`、`user`、`machine`、`machineOrUser`、`guest`。|

## <a name="relationships"></a>关系
|关系|类型|说明|
|:---|:---|:---|
|groupAssignments|[deviceConfigurationGroupAssignment](../resources/intune-deviceconfig-deviceconfigurationgroupassignment.md) 集合|设备配置文件的组分配列表。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|assignments|[deviceConfigurationAssignment](../resources/intune-deviceconfig-deviceconfigurationassignment.md) 集合|设备配置文件的分配列表。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|deviceStatuses|[deviceConfigurationDeviceStatus](../resources/intune-deviceconfig-deviceconfigurationdevicestatus.md) 集合|按设备的设备配置安装状态。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|userStatuses|[deviceConfigurationUserStatus](../resources/intune-deviceconfig-deviceconfigurationuserstatus.md) 集合|按用户的设备配置安装状态。 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|deviceStatusOverview|[deviceConfigurationDeviceOverview](../resources/intune-deviceconfig-deviceconfigurationdeviceoverview.md)|设备配置设备状态概述 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|userStatusOverview|[deviceConfigurationUserOverview](../resources/intune-deviceconfig-deviceconfigurationuseroverview.md)|设备配置用户状态概述 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|deviceSettingStateSummaries|[settingStateDeviceSummary](../resources/intune-deviceconfig-settingstatedevicesummary.md) 集合|设备配置设置状态设备摘要 继承自 [deviceConfiguration](../resources/intune-shared-deviceconfiguration.md)|
|rootCertificatesForServerValidation|[windows81TrustedRootCertificate](../resources/intune-deviceconfig-windows81trustedrootcertificate.md) 集合|指定用于服务器验证的根证书。|
|identityCertificateForClientAuthentication|[windowsCertificateProfileBase](../resources/intune-deviceconfig-windowscertificateprofilebase.md)|指定用于客户端身份验证的标识证书。|
|rootCertificateForClientValidation|[windows81TrustedRootCertificate](../resources/intune-deviceconfig-windows81trustedrootcertificate.md)|指定用于客户端验证的根证书。|

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.windowsWifiEnterpriseEAPConfiguration"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.windowsWifiEnterpriseEAPConfiguration",
  "id": "String (identifier)",
  "lastModifiedDateTime": "String (timestamp)",
  "roleScopeTagIds": [
    "String"
  ],
  "supportsScopeTags": true,
  "deviceManagementApplicabilityRuleOsEdition": {
    "@odata.type": "microsoft.graph.deviceManagementApplicabilityRuleOsEdition",
    "osEditionTypes": [
      "String"
    ],
    "name": "String",
    "ruleType": "String"
  },
  "deviceManagementApplicabilityRuleOsVersion": {
    "@odata.type": "microsoft.graph.deviceManagementApplicabilityRuleOsVersion",
    "minOSVersion": "String",
    "maxOSVersion": "String",
    "name": "String",
    "ruleType": "String"
  },
  "deviceManagementApplicabilityRuleDeviceMode": {
    "@odata.type": "microsoft.graph.deviceManagementApplicabilityRuleDeviceMode",
    "deviceMode": "String",
    "name": "String",
    "ruleType": "String"
  },
  "createdDateTime": "String (timestamp)",
  "description": "String",
  "displayName": "String",
  "version": 1024,
  "preSharedKey": "String",
  "wifiSecurityType": "String",
  "meteredConnectionLimit": "String",
  "ssid": "String",
  "networkName": "String",
  "connectAutomatically": true,
  "connectToPreferredNetwork": true,
  "connectWhenNetworkNameIsHidden": true,
  "proxySetting": "String",
  "proxyManualAddress": "String",
  "proxyManualPort": 1024,
  "proxyAutomaticConfigurationUrl": "String",
  "forceFIPSCompliance": true,
  "networkSingleSignOn": "String",
  "maximumAuthenticationTimeoutInSeconds": 1024,
  "userBasedVirtualLan": true,
  "promptForAdditionalAuthenticationCredentials": true,
  "enablePairwiseMasterKeyCaching": true,
  "maximumPairwiseMasterKeyCacheTimeInMinutes": 1024,
  "maximumNumberOfPairwiseMasterKeysInCache": 1024,
  "enablePreAuthentication": true,
  "maximumPreAuthenticationAttempts": 1024,
  "eapType": "String",
  "trustedServerCertificateNames": [
    "String"
  ],
  "authenticationMethod": "String",
  "innerAuthenticationProtocolForEAPTTLS": "String",
  "outerIdentityPrivacyTemporaryValue": "String",
  "requireCryptographicBinding": true,
  "performServerValidation": true,
  "disableUserPromptForServerValidation": true,
  "authenticationPeriodInSeconds": 1024,
  "authenticationRetryDelayPeriodInSeconds": 1024,
  "eapolStartPeriodInSeconds": 1024,
  "maximumEAPOLStartMessages": 1024,
  "maximumAuthenticationFailures": 1024,
  "cacheCredentials": true,
  "authenticationType": "String"
}
```




