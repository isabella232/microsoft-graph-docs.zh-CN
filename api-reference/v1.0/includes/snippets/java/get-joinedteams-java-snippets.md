---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 1162eae62a9404c1fbfc7f3d8102621a56b29ef5
ms.sourcegitcommit: b18f978808fef800bff9e587464a5f3e18eb7687
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35888853"
---
```java

IGraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

IGroupCollectionPage joinedTeams = graphClient.me().joinedTeams()
    .buildRequest()
    .get();

```