---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 5a81d06ffca52a20223f78e20573bec22064cfbe
ms.sourcegitcommit: 60dfb2ad9ef17f2918c4ee34ebb74f63e32ce2d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37998018"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

let res = await client.api('/me/profile/account')
    .version('beta')
    .get();

```