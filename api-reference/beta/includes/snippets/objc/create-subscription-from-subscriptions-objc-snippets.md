---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 8122c7834528f15440e3e51da2ee901ebefef07c
ms.sourcegitcommit: 9faca60f0cc4ee9d6dce33fd25c72e14b5487d34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "46512287"
---
```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/subscriptions"]]];
[urlRequest setHTTPMethod:@"POST"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

MSGraphSubscription *subscription = [[MSGraphSubscription alloc] init];
[subscription setChangeType:@"created"];
[subscription setNotificationUrl:@"https://webhook.azurewebsites.net/api/send/myNotifyClient"];
[subscription setResource:@"me/mailFolders('Inbox')/messages"];
[subscription setExpirationDateTime: "2016-11-20T18:23:45.9356913Z"];
[subscription setClientState:@"secretClientValue"];
[subscription setLatestSupportedTlsVersion:@"v1_2"];

NSError *error;
NSData *subscriptionData = [subscription getSerializedDataWithError:&error];
[urlRequest setHTTPBody:subscriptionData];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
    completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

        //Request Completed

}];

[meDataTask execute];

```