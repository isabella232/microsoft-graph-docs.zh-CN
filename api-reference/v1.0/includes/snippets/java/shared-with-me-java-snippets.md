---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 139f0b81531af87133780d9d7177cf044198d7f8
ms.sourcegitcommit: b18f978808fef800bff9e587464a5f3e18eb7687
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35883059"
---
```java

IGraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

IDriveItemCollectionPage sharedWithMe = graphClient.me().drive()
    .sharedWithMe()
    .buildRequest()
    .get();

```