---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 3c47d453f343f0d152befcbada8edbe8af91b2c6
ms.sourcegitcommit: 5a1373f2ccd9ee813fc60d42e7ac6b115b5f9f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "44336762"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

let res = await client.api('/contacts')
    .version('beta')
    .header('ConsistencyLevel','eventual')
    .search('displayName:wa')
    .get();

```