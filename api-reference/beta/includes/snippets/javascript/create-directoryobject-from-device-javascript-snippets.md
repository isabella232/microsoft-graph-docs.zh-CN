---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 7de623a58979551861af4088cedd3bb548c5ff9c
ms.sourcegitcommit: 0545b031585e605dc3a0fde481015f51f79819c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45224762"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

const directoryObject = {
  @odata.id: "https://graph.microsoft.com/beta/directoryObjects/{id}"
};

let res = await client.api('/devices/{id}/registeredUsers/$ref')
    .version('beta')
    .post(directoryObject);

```