---
title: 删除 passwordlessMicrosoftAuthenticatorAuthenticationMethod
description: 删除一个 passwordlessMicrosoftAuthenticatorAuthenticationMethod 对象。
author: mmcla
localization_priority: Normal
ms.prod: microsoft-identity-platform
doc_type: apiPageType
ms.openlocfilehash: 42d7ffe92488a7166356b0e43688a17f2935b503
ms.sourcegitcommit: ea3b1a8b781a347015d9542826c5c0c24d50d35d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49352387"
---
# <a name="delete-passwordlessmicrosoftauthenticatorauthenticationmethod"></a>删除 passwordlessMicrosoftAuthenticatorAuthenticationMethod
命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

删除用户的 [Microsoft 身份验证 Passwordless Phone 登录方法](../resources/passwordlessmicrosoftauthenticatorauthenticationmethod.md) 对象。

> [!NOTE]
> 在 Api 位于 Mirosoft Graph beta 过程中时，规划用于管理 Microsoft 身份验证器应用程序的 Api 的大量架构更改。 由于调用模式将发生更改，因此我们建议您不要对这些 Api 进行生产依赖。


## <a name="permissions"></a>权限
要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。

|权限类型|从最高特权到最少特权) 对自己 (的权限|对其他人进行操作的权限 (从至少到最高特权) |
|:---|:---|:--|
|委派（工作或学校帐户）|不支持。|UserAuthenticationMethod
|委派（个人 Microsoft 帐户）|不支持。|不支持。
|应用程序|不支持。|不支持。

对于在其他用户上执行管理的委派方案，管理员需要以下 [角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)之一：

* 全局管理员
* 特权身份验证管理员
* 身份验证管理员

## <a name="http-request"></a>HTTP 请求

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /users/{id | userPrincipalName}/authentication/passwordlessMicrosoftAuthenticatorMethods/{id}
```

## <a name="request-headers"></a>请求标头
|名称|说明|
|:---|:---|
|Authorization|Bearer {token}。必需。|

## <a name="request-body"></a>请求正文
请勿提供此方法的请求正文。

## <a name="response"></a>响应

如果成功，此方法返回 `204 No Content` 响应代码。它不在响应正文中返回任何内容。

## <a name="examples"></a>示例

### <a name="request"></a>请求

# <a name="http"></a>[HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "delete_passwordlessmicrosoftauthenticatorauthenticationmethod"
}
-->
``` http
DELETE https://graph.microsoft.com/beta/users/kim@contoso.com/authentication/passwordlessMicrosoftAuthenticatorMethods/R18B3t8Ogh9XIOGmPt81d6p_KXJs1YTxfGgGqeVFJSM1
```
# <a name="c"></a>[C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/delete-passwordlessmicrosoftauthenticatorauthenticationmethod-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascript"></a>[JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/delete-passwordlessmicrosoftauthenticatorauthenticationmethod-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-c"></a>[Objective-C](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/delete-passwordlessmicrosoftauthenticatorauthenticationmethod-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="java"></a>[Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/delete-passwordlessmicrosoftauthenticatorauthenticationmethod-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---



### <a name="response"></a>响应
下面展示了示例响应。
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

