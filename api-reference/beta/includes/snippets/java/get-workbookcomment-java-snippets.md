---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 6027cf2647bea5816ee3ea8d77b40c60adf89439
ms.sourcegitcommit: 342516a52b69fcda31442b130eb6bd7e2c8a0066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48977499"
---
```java

IGraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

WorkbookComment workbookComment = graphClient.drive().items("{id}").workbook().comments("{id}")
    .buildRequest()
    .get();

```