---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 64b7670e4d32322d0e486185cc8e840dc56462c0
ms.sourcegitcommit: af4b2fc18449c33979cf6d75bd680f40602ba708
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48608168"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

let res = await client.api('/me/drive/recent')
    .get();

```