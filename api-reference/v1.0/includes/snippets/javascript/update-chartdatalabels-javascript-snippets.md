---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 2865322a7a1bd729244ba09c4d52a9e789614b6b
ms.sourcegitcommit: 0329bbcd5f1b09a2a6c5f935a30c4560b6eed492
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36636889"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

const workbookChartDataLabels = {
  position: "position-value",
  showValue: true,
  showSeriesName: true,
  showCategoryName: true,
  showLegendKey: true
};

let res = await client.api('/me/drive/items/{id}/workbook/worksheets/{id|name}/charts/{name}/dataLabels')
    .update(workbookChartDataLabels);

```