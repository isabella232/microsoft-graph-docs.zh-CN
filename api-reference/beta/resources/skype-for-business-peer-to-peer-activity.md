---
title: Skype for Business 对等活动报表
description: 你可以在组织中获取对等活动的详细信息。 为组织调查、计划和做出其他业务决策时，便会发现这些详细信息非常有用。
localization_priority: Normal
ms.prod: reports
author: pranoychaudhuri
doc_type: conceptualPageType
ms.openlocfilehash: 76411b36259ade242be327525bbc1d65c7edd021
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47997597"
---
# <a name="skype-for-business-peer-to-peer-activity-reports"></a>Skype for Business 对等活动报表

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

你可以在组织中获取对等活动的详细信息。 为组织调查、计划和做出其他业务决策时，便会发现这些详细信息非常有用。

> **注意：** 若要详细了解不同的报表视图和名称，请参阅 [Microsoft 365 reports-Skype For business 对等活动](https://support.office.com/client/Skype-for-Business-Online-peertopeer-activity-d3b2d569-4ee9-44b8-92bf-d518142f0713)。

## <a name="reports"></a>报表

| 函数                                 | CSV 返回类型 | JSON 返回类型                         | 说明                              |
| :--------------------------------------- | :-------------- | :--------------------------------------- | ---------------------------------------- |
| [获取活动数](../api/reportroot-getskypeforbusinesspeertopeeractivitycounts.md) | Stream          | [skypeForBusinessPeerToPeerActivityCounts](../resources/skypeforbusinesspeertopeeractivitycounts.md) | 获取使用情况趋势，即组织中召开的会话的次数和类型。 会话类型包括 IM、音频、视频、应用共享和文件传输。 |
| [获取用户数](../api/reportroot-getskypeforbusinesspeertopeeractivityusercounts.md) | Stream          | [skypeForBusinessPeerToPeerActivityUserCounts](../resources/skypeforbusinesspeertopeeractivityusercounts.md) | 获取使用情况趋势，即组织中召开的对等会话的唯一用户数和类型。 对等会话类型包括 IM、音频、视频、应用共享和文件传输。 |
| [获取分钟数](../api/reportroot-getskypeforbusinesspeertopeeractivityminutecounts.md) | Stream          | [skypeForBusinessPeerToPeerActivityMinuteCounts](../resources/skypeforbusinesspeertopeeractivityminutecounts.md) | 获取使用情况趋势，即组织中召开的对等会话的时长（以分钟为单位）和类型。 会话类型包括音频和视频。 |


