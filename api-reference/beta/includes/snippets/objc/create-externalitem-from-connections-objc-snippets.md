---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 8c683e37a74337bcb784c2519a2ddbbf2a884c6a
ms.sourcegitcommit: 7e1993d64cc6d3145ae0ca984fefe74772b6052b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "47938490"
---
```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/connections/contosohr/items/TSP228082938"]]];
[urlRequest setHTTPMethod:@"PUT"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

MSGraphExternalItem *externalItem = [[MSGraphExternalItem alloc] init];
NSMutableArray *aclList = [[NSMutableArray alloc] init];
MSGraphAcl *acl = [[MSGraphAcl alloc] init];
[acl setType: [MSGraphAclType user]];
[acl setValue:@"49103559-feac-4575-8b94-254814dfca72"];
[acl setAccessType: [MSGraphAccessType deny]];
[acl setIdentitySource:@"azureActiveDirectory"];
[aclList addObject: acl];
[externalItem setAcl:aclList];
MSGraphProperties *properties = [[MSGraphProperties alloc] init];
[properties setTitle:@"Error in the payment gateway"];
[properties setPriority: 1];
[properties setAssignee:@"john@contoso.com"];
[externalItem setProperties:properties];
MSGraphExternalItemContent *content = [[MSGraphExternalItemContent alloc] init];
[content setValue:@"<h1>Error in payment gateway</h1><p>Error details...</p>"];
[content setType: [MSGraphExternalItemContentType html]];
[externalItem setContent:content];

NSError *error;
NSData *externalItemData = [externalItem getSerializedDataWithError:&error];
[urlRequest setHTTPBody:externalItemData];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
    completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

        //Request Completed

}];

[meDataTask execute];

```