---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 986b95372365eafd50770d483b98a6c41ce56847
ms.sourcegitcommit: 342516a52b69fcda31442b130eb6bd7e2c8a0066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48983599"
---
```java

IGraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

WorkbookRangeFont workbookRangeFont = new WorkbookRangeFont();
workbookRangeFont.italic = true;
workbookRangeFont.size = 26d;

graphClient.me().drive().items("{id}").workbook().worksheets("{sheet-id}")
    .range("$B$1").format().font()
    .buildRequest()
    .patch(workbookRangeFont);

```