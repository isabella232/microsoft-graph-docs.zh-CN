---
description: 自动生成文件。 请不要修改
ms.openlocfilehash: 7863f3b9725dc8696546bd8a3dbaf0f16066358d
ms.sourcegitcommit: d4114bac58628527611e83e436132c6581a19c52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44217244"
---
```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/v1.0/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/teams/788b75d2-a911-48c0-a5e2-dc98480457e3/schedule/offershiftrequests"]]];
[urlRequest setHTTPMethod:@"POST"];
[urlRequest setValue:@"Bearer {token}" forHTTPHeaderField:@"Authorization"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

MSGraphOfferShiftRequest *offerShiftRequest = [[MSGraphOfferShiftRequest alloc] init];
[offerShiftRequest setSenderShiftId:@"SHFT_f7e484ed-fdd6-421c-92d9-0bc9e62e2c29"];
[offerShiftRequest setSenderMessage:@"Having a family emergency, could you take this shift for me?"];
[offerShiftRequest setRecipientUserId:@"fe278b61-21ac-4872-8b41-1962bbb98e3c"];

NSError *error;
NSData *offerShiftRequestData = [offerShiftRequest getSerializedDataWithError:&error];
[urlRequest setHTTPBody:offerShiftRequestData];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
    completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

        //Request Completed

}];

[meDataTask execute];

```