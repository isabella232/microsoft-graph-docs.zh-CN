---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 0198f2abb444a6bb9047b0a556dd90833c920bab
ms.sourcegitcommit: 60dfb2ad9ef17f2918c4ee34ebb74f63e32ce2d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37995451"
---
```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var extensionProperties = await graphClient.Applications["{id}"].ExtensionProperties
    .Request()
    .GetAsync();

```