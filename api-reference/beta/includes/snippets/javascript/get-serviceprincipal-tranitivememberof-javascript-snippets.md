---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: c81c3627b93ae086d23136983dd69443a3b5d959
ms.sourcegitcommit: 5a1373f2ccd9ee813fc60d42e7ac6b115b5f9f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "44336777"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

let res = await client.api('/servicePrincipals/{id}/transitiveMemberOf')
    .version('beta')
    .get();

```