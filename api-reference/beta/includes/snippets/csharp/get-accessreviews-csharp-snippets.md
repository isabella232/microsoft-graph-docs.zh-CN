---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 312a16542f03471774d4f56a28b13abe3533b19b
ms.sourcegitcommit: 5f643d3b3f71a9711963c8953da2188539fc9b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41119513"
---
```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var accessReviews = await graphClient.AccessReviews
    .Request()
    .Filter("businessFlowTemplateId+eq+'6e4f3d20-c5c3-407f-9695-8460952bcc68',")
    .Skip(0)
    .Top(100)
    .GetAsync();

```