---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: e679eeec9839628e17c8b6f78483a0fe8115d0b9
ms.sourcegitcommit: c4d6ccd343a6b298a2aa844f1bad66c736487251
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2020
ms.locfileid: "42589259"
---
```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/policies/tokenLifetimePolicies/{id}"]]];
[urlRequest setHTTPMethod:@"PATCH"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

MSGraphTokenLifetimePolicy *tokenLifetimePolicy = [[MSGraphTokenLifetimePolicy alloc] init];
NSMutableArray *definitionList = [[NSMutableArray alloc] init];
[definitionList addObject: @"definition-value"];
[tokenLifetimePolicy setDefinition:definitionList];
[tokenLifetimePolicy setDisplayName:@"displayName-value"];
[tokenLifetimePolicy setIsOrganizationDefault: true];
[tokenLifetimePolicy setType:@"type-value"];

NSError *error;
NSData *tokenLifetimePolicyData = [tokenLifetimePolicy getSerializedDataWithError:&error];
[urlRequest setHTTPBody:tokenLifetimePolicyData];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
    completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

        //Request Completed

}];

[meDataTask execute];

```