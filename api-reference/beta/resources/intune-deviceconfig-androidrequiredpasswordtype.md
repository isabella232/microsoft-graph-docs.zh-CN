---
title: androidRequiredPasswordType 枚举类型
description: Android 必需的密码类型。
author: dougeby
localization_priority: Normal
ms.prod: intune
doc_type: enumPageType
ms.openlocfilehash: 5842974b164361f834041e741554045428a7b95a
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49231652"
---
# <a name="androidrequiredpasswordtype-enum-type"></a>androidRequiredPasswordType 枚举类型

命名空间：microsoft.graph

> **重要说明：** /Beta 版本下的 Microsoft Graph Api 可能会发生更改;不支持生产使用。

> **注意：** 适用于 Intune 的 Microsoft Graph API 需要适用于租户的 [活动 Intune 许可证](https://go.microsoft.com/fwlink/?linkid=839381)。

Android 必需的密码类型。

## <a name="members"></a>成员
|成员|值|说明|
|:---|:---|:---|
|deviceDefault|0|设备默认值，无意向。|
|字母|1|要求字母密码。|
|字母数字|双面|需要字母数字密码。|
|alphanumericWithSymbols|第三章|需要带符号的字母数字密码。|
|lowSecurityBiometric|4 |要求低安全基于生物特征的密码。|
|位数|5 |需要数字密码。|
|numericComplex|6 |需要数字复杂密码。|
|任意|7 |需要密码或模式，可以接受。|




