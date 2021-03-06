---
title: 电子邮件应用使用情况报表
description: 电子邮件应用使用情况报表可用于了解用于连接到 Exchange Online 的电子邮件应用数。 此外，还可以了解使用的 Outlook 应用版本，这有助于跟进应升级到受支持 Outlook 版本的用户。
localization_priority: Normal
author: pranoychaudhuri
ms.prod: reports
doc_type: conceptualPageType
ms.openlocfilehash: 18403a0040672c2c056b9cc03246e29a91639e45
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48069125"
---
# <a name="email-app-usage-reports"></a>电子邮件应用使用情况报表

命名空间：microsoft.graph

电子邮件应用使用情况报表可用于了解用于连接到 Exchange Online 的电子邮件应用数。 此外，还可以了解使用的 Outlook 应用版本，这有助于跟进应升级到受支持 Outlook 版本的用户。

> **注意：** 若要详细了解不同的报表视图和名称，请参阅 [Microsoft 365 报表-电子邮件应用程序使用](https://support.office.com/client/Email-apps-usage-c2ce12a2-934f-4dd4-ba65-49b02be4703d)。

## <a name="reports"></a>报告

| 函数                                 | 返回类型 | 说明                              |
| :--------------------------------------- | :---------- | :--------------------------------------- |
| [获取用户详细信息](../api/reportroot-getemailappusageuserdetail.md) | Stream      | 获取用户在不同电子邮件应用中执行的活动的详细信息。 |
| [获取应用用户数](../api/reportroot-getemailappusageappsusercounts.md) | Stream      | 获取每个电子邮件应用的唯一用户数。 |
| [获取用户数](../api/reportroot-getemailappusageusercounts.md) | Stream      | 获取使用任意电子邮件应用连接到 Exchange Online 的唯一用户数。 |
| [获取版本用户数](../api/reportroot-getemailappusageversionsusercounts.md) | Stream      | 按 Outlook 桌面版获取唯一用户数。 |

