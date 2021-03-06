---
title: OneDrive 活动报表
description: 您可以通过查看其与 OneDrive 上的文件的交互，获取获得使用 OneDrive 的每个用户的活动。 它还可帮助您了解通过显示共享文件数而进行的协作级别。
localization_priority: Normal
ms.prod: reports
author: pranoychaudhuri
doc_type: conceptualPageType
ms.openlocfilehash: 656d722a9d63e460cd4b62e87a0b2fd8483e37c7
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48092333"
---
# <a name="onedrive-activity-reports"></a>OneDrive 活动报表

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

您可以通过查看其与 OneDrive 上的文件的交互，获取获得使用 OneDrive 的每个用户的活动。 它还可帮助您了解通过显示共享文件数而进行的协作级别。

> **注意：** 若要详细了解不同的报表视图和名称，请参阅 [Microsoft 365 reports-OneDrive For business 活动](https://support.office.com/client/OneDrive-for-Business-user-activity-8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353)。

## <a name="reports"></a>报表

| 函数                                 | CSV 返回类型 | JSON 返回类型                         | 说明                              |
| :--------------------------------------- | :-------------- | :--------------------------------------- | ---------------------------------------- |
| [获取用户详细信息](../api/reportroot-getonedriveactivityuserdetail.md) | Stream          | [oneDriveActivityUserDetail](../resources/onedriveactivityuserdetail.md) | 获取用户执行的 OneDrive 活动的详细信息。 |
| [获取用户数](../api/reportroot-getonedriveactivityusercounts.md) | Stream          | [siteActivitySummary](../resources/siteactivitysummary.md) | 获取 OneDrive 活跃用户数趋势。 |
| [获取文件数](../api/reportroot-getonedriveactivityfilecounts.md) | Stream          | [siteActivitySummary](../resources/siteactivitysummary.md) | 获取对任意 OneDrive 帐户执行文件交互的唯一许可用户数。 |


