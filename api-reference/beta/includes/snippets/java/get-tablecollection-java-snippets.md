---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: debb2433b0ca23dd9e1f6b77f3495f543bb5678e
ms.sourcegitcommit: 342516a52b69fcda31442b130eb6bd7e2c8a0066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48969374"
---
```java

IGraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

IWorkbookTableCollectionPage tables = graphClient.me().drive().items("{id}").workbook().tables()
    .buildRequest()
    .get();

```