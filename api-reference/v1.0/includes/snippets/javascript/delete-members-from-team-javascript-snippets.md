---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 816943f8ff899288f9f8ef428f534bda736d8492
ms.sourcegitcommit: a9f0fde9924ad184d315bb2de43c2610002409f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48315518"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

let res = await client.api('/teams/{teamsId}/members/{membership-id}')
    .delete();

```