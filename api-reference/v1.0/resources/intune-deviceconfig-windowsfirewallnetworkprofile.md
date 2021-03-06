---
title: windowsFirewallNetworkProfile 资源类型
description: Windows 防火墙配置文件策略。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: resourcePageType
ms.openlocfilehash: f95258e83603f29990af120624ae91b6a389df74
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48091535"
---
# <a name="windowsfirewallnetworkprofile-resource-type"></a>windowsFirewallNetworkProfile 资源类型

命名空间：microsoft.graph

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的[活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

Windows 防火墙配置文件策略。

## <a name="properties"></a>属性
|属性|类型|说明|
|:---|:---|:---|
|firewallEnabled|[stateManagementSetting](../resources/intune-deviceconfig-statemanagementsetting.md)|将主机设备配置为允许或阻止网络配置文件的防火墙和高级安全强制实施。 可取值为：`notConfigured`、`blocked`、`allowed`。|
|stealthModeBlocked|布尔值|阻止服务器在隐藏模式下运行。 当 StealthModeRequired 和 StealthModeBlocked 均为 true 时，StealthModeBlocked 优先。|
|incomingTrafficBlocked|布尔值|将防火墙配置为阻止所有传入通信，而不考虑其他策略设置。 当 IncomingTrafficRequired 和 IncomingTrafficBlocked 均为 true 时，IncomingTrafficBlocked 优先。|
|unicastResponsesToMulticastBroadcastsBlocked|布尔值|配置防火墙以阻止对多播广播流量的单播响应。 当 UnicastResponsesToMulticastBroadcastsRequired 和 UnicastResponsesToMulticastBroadcastsBlocked 均为 true 时，UnicastResponsesToMulticastBroadcastsBlocked 优先。|
|inboundNotificationsBlocked|布尔值|阻止阻止在某个应用程序侦听某个端口时显示通知的防火墙。 当 InboundNotificationsRequired 和 InboundNotificationsBlocked 均为 true 时，InboundNotificationsBlocked 优先。|
|authorizedApplicationRulesFromGroupPolicyMerged|布尔值|将防火墙配置为将组策略中的已授权应用程序规则与本地存储合并，而不是忽略本地存储规则。 当 AuthorizedApplicationRulesFromGroupPolicyNotMerged 和 AuthorizedApplicationRulesFromGroupPolicyMerged 均为 true 时，AuthorizedApplicationRulesFromGroupPolicyMerged 优先。|
|globalPortRulesFromGroupPolicyMerged|布尔值|将防火墙配置为将组策略中的全局端口规则与本地存储合并，而不是忽略本地存储规则。 当 GlobalPortRulesFromGroupPolicyNotMerged 和 GlobalPortRulesFromGroupPolicyMerged 均为 true 时，GlobalPortRulesFromGroupPolicyMerged 优先。|
|connectionSecurityRulesFromGroupPolicyMerged|布尔值|将防火墙配置为将组策略中的连接安全规则与本地存储中的连接进行合并，而不是忽略本地存储规则。 当 ConnectionSecurityRulesFromGroupPolicyNotMerged 和 ConnectionSecurityRulesFromGroupPolicyMerged 均为 true 时，ConnectionSecurityRulesFromGroupPolicyMerged 优先。|
|outboundConnectionsBlocked|布尔值|默认情况下，将防火墙配置为阻止所有传出连接。 当 OutboundConnectionsRequired 和 OutboundConnectionsBlocked 均为 true 时，OutboundConnectionsBlocked 优先。 此设置将应用于 Windows 版本1809及更高版本。|
|inboundConnectionsBlocked|布尔值|默认情况下，将防火墙配置为阻止所有传入连接。 当 InboundConnectionsRequired 和 InboundConnectionsBlocked 均为 true 时，InboundConnectionsBlocked 优先。|
|securedPacketExemptionAllowed|布尔值|将防火墙配置为允许主机计算机对该流量的未经请求的网络流量进行响应，即使 stealthModeBlocked 设置为 true，该流量仍受 IPSec 保护。 当 SecuredPacketExemptionBlocked 和 SecuredPacketExemptionAllowed 均为 true 时，SecuredPacketExemptionAllowed 优先。|
|policyRulesFromGroupPolicyMerged|布尔值|将防火墙配置为将组策略中的防火墙规则策略与本地存储中的防火墙规则策略相合并，而不是忽略本地存储规则。 当 PolicyRulesFromGroupPolicyNotMerged 和 PolicyRulesFromGroupPolicyMerged 均为 true 时，PolicyRulesFromGroupPolicyMerged 优先。|

## <a name="relationships"></a>关系
无

## <a name="json-representation"></a>JSON 表示形式
下面是资源的 JSON 表示形式。
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.windowsFirewallNetworkProfile"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.windowsFirewallNetworkProfile",
  "firewallEnabled": "String",
  "stealthModeBlocked": true,
  "incomingTrafficBlocked": true,
  "unicastResponsesToMulticastBroadcastsBlocked": true,
  "inboundNotificationsBlocked": true,
  "authorizedApplicationRulesFromGroupPolicyMerged": true,
  "globalPortRulesFromGroupPolicyMerged": true,
  "connectionSecurityRulesFromGroupPolicyMerged": true,
  "outboundConnectionsBlocked": true,
  "inboundConnectionsBlocked": true,
  "securedPacketExemptionAllowed": true,
  "policyRulesFromGroupPolicyMerged": true
}
```









