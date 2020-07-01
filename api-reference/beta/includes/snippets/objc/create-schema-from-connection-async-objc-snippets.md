---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: f7cb915b6d989231a5d7a24d2f86c5fd6bfee6ea
ms.sourcegitcommit: e20c113409836115f338dcfe3162342ef3bd6a4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45008611"
---
```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/connections/contosohr/schema"]]];
[urlRequest setHTTPMethod:@"POST"];
[urlRequest setValue:@"respond-async" forHTTPHeaderField:@"Prefer"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

MSGraphSchema *schema = [[MSGraphSchema alloc] init];
[schema setBaseType:@"microsoft.graph.externalItem"];
NSMutableArray *propertiesList = [[NSMutableArray alloc] init];
MSGraphProperty *properties = [[MSGraphProperty alloc] init];
[properties setName:@"ticketTitle"];
[properties setType: [MSGraphPropertyType String]];
[properties setIsSearchable:@"true"];
[properties setIsRetrievable:@"true"];
NSMutableArray *labelsList = [[NSMutableArray alloc] init];
[labelsList addObject: @"title"];
[properties setLabels:labelsList];
[propertiesList addObject: properties];
MSGraphProperty *properties = [[MSGraphProperty alloc] init];
[properties setName:@"priority"];
[properties setType: [MSGraphPropertyType String]];
[properties setIsQueryable:@"true"];
[properties setIsRetrievable:@"true"];
[properties setIsRefinable:@"true"];
[properties setIsSearchable:@"false"];
[propertiesList addObject: properties];
MSGraphProperty *properties = [[MSGraphProperty alloc] init];
[properties setName:@"assignee"];
[properties setType: [MSGraphPropertyType String]];
[properties setIsRetrievable:@"true"];
[propertiesList addObject: properties];
[schema setProperties:propertiesList];

NSError *error;
NSData *schemaData = [schema getSerializedDataWithError:&error];
[urlRequest setHTTPBody:schemaData];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
    completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

        //Request Completed

}];

[meDataTask execute];

```