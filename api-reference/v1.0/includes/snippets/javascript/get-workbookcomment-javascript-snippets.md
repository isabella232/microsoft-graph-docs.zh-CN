---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: be70e57512dca1a4c79b1e663eceaddd95c9f6df
ms.sourcegitcommit: 2f78ac96a9b0462626a242429055ef824590bd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2020
ms.locfileid: "41497253"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

let res = await client.api('/drive/items/{id}/workbook/comments/{id}')
    .get();

```