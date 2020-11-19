---
description: 自动生成的文件。请勿修改
ms.openlocfilehash: cb9649c38b1bec7283f33ad7c376035a9d88d8ba
ms.sourcegitcommit: eb536655ffd8d49ae258664f35c50a8263238400
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49221826"
---
```javascript

const options = {
    authProvider,
};

const client = Client.init(options);

const accessReview = {
  displayName: "Test create",
  descriptionForAdmins: "New scheduled access review",
  descriptionForReviewers: "If you have any questions, contact jerry@contoso.com",
  scope: {
    query: "/groups/b7a059cb-038a-4802-8fc9-b9d1ed0c4444/transitiveMembers",
    queryType: "MicrosoftGraph"
  },
  reviewers: [
    {
      query: "/users/7eae4444-d425-48b2-adf2-3c777f6256f3",
      queryType: "MicrosoftGraph",
      queryRoot: "decisions"
    }
  ],
  settings: {
    mailNotificationsEnabled: true,
    reminderNotificationsEnabled: true,
    justificationRequiredOnApproval: true,
    defaultDecisionEnabled: false,
    defaultDecision: "None",
    instanceDurationInDays: 1,
    autoApplyDecisionsEnabled: false,
    recommendationsEnabled: true,
    recurrence: {
      pattern: {
        type: "weekly",
        interval: 1
      },
      range: {
        type: "noEnd",
        startDate: "2020-09-08T12:02:30.667Z"
      }
    }
  }
};

let res = await client.api('/accessReviews')
    .version('beta')
    .post(accessReview);

```