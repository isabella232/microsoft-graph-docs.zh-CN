---
title: managedAppDataEncryptionType 枚举类型
description: 表示为托管应用程序加密应用程序数据的级别
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: enumPageType
ms.openlocfilehash: 1bc52b0fa05a65adfb3e195d0a38c9bebd78e6c3
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49267031"
---
# <a name="managedappdataencryptiontype-enum-type"></a>managedAppDataEncryptionType 枚举类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

表示为托管应用程序加密应用程序数据的级别

## <a name="members"></a>成员
|成员|值|说明|
|:---|:---|:---|
|useDeviceSettings|0|应用程序数据根据设备上的默认设置进行加密。|
|afterDeviceRestart|1|重新启动设备时对应用数据进行加密。|
|whenDeviceLockedExceptOpenFiles|双面|设备锁定时，与此策略关联的应用数据将被加密，但打开的文件中的数据除外|
|whenDeviceLocked|第三章|设备锁定时，与此策略关联的应用数据将被加密|




