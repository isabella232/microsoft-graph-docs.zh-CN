---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: c57091367acc0572eb1139bb31f4f39ba026f557
ms.sourcegitcommit: af4b2fc18449c33979cf6d75bd680f40602ba708
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48612293"
---
```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/me/drive/items/{id}/workbook/worksheets/{id|name}/charts/{name}/datalabels"]]];
[urlRequest setHTTPMethod:@"PATCH"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

MSGraphWorkbookChartDataLabels *workbookChartDataLabels = [[MSGraphWorkbookChartDataLabels alloc] init];
[workbookChartDataLabels setPosition:@"position-value"];
[workbookChartDataLabels setShowValue: true];
[workbookChartDataLabels setShowSeriesName: true];
[workbookChartDataLabels setShowCategoryName: true];
[workbookChartDataLabels setShowLegendKey: true];

NSError *error;
NSData *workbookChartDataLabelsData = [workbookChartDataLabels getSerializedDataWithError:&error];
[urlRequest setHTTPBody:workbookChartDataLabelsData];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
    completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

        //Request Completed

}];

[meDataTask execute];

```