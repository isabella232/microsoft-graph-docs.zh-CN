---
title: 邮箱使用情况报表
description: 邮箱使用情况报表可用于获取使用邮箱的用户及其活动级别（主要是以发送和接收的电子邮件数为依据）。 此外，还可以了解每个邮箱占用的存储空间，以及即将达到存储配额的邮箱数。
localization_priority: Priority
author: pranoychaudhuri
ms.prod: reports
doc_type: conceptualPageType
ms.openlocfilehash: 5508b20aaa7a4727a49a780e8ebdcffd3acc388b
ms.sourcegitcommit: acdf972e2f25fef2c6855f6f28a63c0762228ffa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48083048"
---
# <a name="mailbox-usage-reports"></a>邮箱使用情况报表

命名空间：microsoft.graph

邮箱使用情况报表可用于获取使用邮箱的用户及其活动级别（主要是以发送和接收的电子邮件数为依据）。 此外，还可以了解每个邮箱占用的存储空间，以及即将达到存储配额的邮箱数。

> **备注：** 若要了解不同报表视图和名称的详细信息，请参阅 [Microsoft 365 报表 - 邮箱使用情况](https://support.office.com/client/Mailbox-usage-beffbe01-ce2d-4614-9ae5-7898868e2729)。

## <a name="reports"></a>报告

| 函数                                 | 返回类型 | 说明                              |
| :--------------------------------------- | :---------- | :--------------------------------------- |
| [获取邮箱详细信息](../api/reportroot-getmailboxusagedetail.md) | Stream      | 获取邮箱使用情况的详细信息。         |
| [获取邮箱数](../api/reportroot-getmailboxusagemailboxcounts.md) | Stream      | 获取组织中的用户邮箱总数和报表周期内的每日活跃邮箱数。 如果用户发送或阅读任何电子邮件，则将邮箱视为活跃邮箱。 |
| [获取配额状态邮箱数](../api/reportroot-getmailboxusagequotastatusmailboxcounts.md) | Stream      | 获取每个配额类别中的用户邮箱数。 |
| [获取存储](../api/reportroot-getmailboxusagestorage.md) | Stream      | 获取组织使用的存储空间。 |

