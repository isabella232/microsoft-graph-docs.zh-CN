---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: a569618e32e7434ee3e943cf430ba0e9fe263986
ms.sourcegitcommit: a3fc420a5639c0f4e89af2b602db17392e176802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48222949"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

let res = await client.api('/trustFramework/keySets/{id}/getActiveKey')
    .version('beta')
    .get();

```