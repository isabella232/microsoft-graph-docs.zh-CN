---
author: JeremyKelley
ms.author: jeremyke
title: 从捆绑包中删除项目
description: 从 Driveitem 的捆绑包中删除项目
localization_priority: Normal
ms.prod: sharepoint
doc_type: apiPageType
ms.openlocfilehash: ff7f292be35b59f17465e65517174746faddca1a
ms.sourcegitcommit: 2c62457e57467b8d50f21b255b553106a9a5d8d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "35944805"
---
# <a name="remove-item-from-bundle"></a><span data-ttu-id="13a04-103">从捆绑包中删除项目</span><span class="sxs-lookup"><span data-stu-id="13a04-103">Remove item from bundle</span></span>

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

<span data-ttu-id="13a04-104">从[捆绑包][]中删除项目。</span><span class="sxs-lookup"><span data-stu-id="13a04-104">Remove an item from a [bundle][].</span></span>

## <a name="permissions"></a><span data-ttu-id="13a04-105">权限</span><span class="sxs-lookup"><span data-stu-id="13a04-105">Permissions</span></span>

<span data-ttu-id="13a04-p101">要调用此 API，需要以下权限之一。要了解详细信息，包括如何选择权限的信息，请参阅[权限](/graph/permissions-reference)。</span><span class="sxs-lookup"><span data-stu-id="13a04-p101">One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).</span></span>

|<span data-ttu-id="13a04-108">权限类型</span><span class="sxs-lookup"><span data-stu-id="13a04-108">Permission type</span></span>      | <span data-ttu-id="13a04-109">权限（从最低特权到最高特权）</span><span class="sxs-lookup"><span data-stu-id="13a04-109">Permissions (from least to most privileged)</span></span>              |
|:--------------------|:---------------------------------------------------------|
|<span data-ttu-id="13a04-110">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="13a04-110">Delegated (work or school account)</span></span> | <span data-ttu-id="13a04-111">不支持。</span><span class="sxs-lookup"><span data-stu-id="13a04-111">Not supported.</span></span>                             |
|<span data-ttu-id="13a04-112">委派（个人 Microsoft 帐户）</span><span class="sxs-lookup"><span data-stu-id="13a04-112">Delegated (personal Microsoft account)</span></span> | <span data-ttu-id="13a04-113">Files.ReadWrite、Files.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="13a04-113">Files.ReadWrite, Files.ReadWrite.All</span></span>   |
|<span data-ttu-id="13a04-114">应用程序</span><span class="sxs-lookup"><span data-stu-id="13a04-114">Application</span></span>          | <span data-ttu-id="13a04-115">不支持。</span><span class="sxs-lookup"><span data-stu-id="13a04-115">Not supported.</span></span>                                           |

## <a name="http-request"></a><span data-ttu-id="13a04-116">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="13a04-116">HTTP request</span></span>

```http
DELETE /drive/bundles/{bundle-id}/children/{item-id}
```

## <a name="request-headers"></a><span data-ttu-id="13a04-117">请求标头</span><span class="sxs-lookup"><span data-stu-id="13a04-117">Request headers</span></span>

| <span data-ttu-id="13a04-118">名称</span><span class="sxs-lookup"><span data-stu-id="13a04-118">Name</span></span>          | <span data-ttu-id="13a04-119">说明</span><span class="sxs-lookup"><span data-stu-id="13a04-119">Description</span></span>  |
|:------------- |:------------ |
| <span data-ttu-id="13a04-120">Authorization</span><span class="sxs-lookup"><span data-stu-id="13a04-120">Authorization</span></span> | <span data-ttu-id="13a04-121">持有者 \{token\}。</span><span class="sxs-lookup"><span data-stu-id="13a04-121">Bearer \{token\}.</span></span> <span data-ttu-id="13a04-122">必需。</span><span class="sxs-lookup"><span data-stu-id="13a04-122">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="13a04-123">请求正文</span><span class="sxs-lookup"><span data-stu-id="13a04-123">Request body</span></span>

<span data-ttu-id="13a04-124">请勿为此方法提供请求正文。</span><span class="sxs-lookup"><span data-stu-id="13a04-124">Do not supply a request body with this method.</span></span>

## <a name="response"></a><span data-ttu-id="13a04-125">响应</span><span class="sxs-lookup"><span data-stu-id="13a04-125">Response</span></span>

<span data-ttu-id="13a04-126">如果成功, 响应为`204 No Content`。</span><span class="sxs-lookup"><span data-stu-id="13a04-126">If successful, the response is `204 No Content`.</span></span>

<span data-ttu-id="13a04-127">阅读 "[错误响应][error-response]" 主题, 了解有关如何返回错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="13a04-127">Read the [Error Responses][error-response] topic for more info about how errors are returned.</span></span>

## <a name="example"></a><span data-ttu-id="13a04-128">示例</span><span class="sxs-lookup"><span data-stu-id="13a04-128">Example</span></span>

### <a name="request"></a><span data-ttu-id="13a04-129">请求</span><span class="sxs-lookup"><span data-stu-id="13a04-129">Request</span></span>


# <a name="httptabhttp"></a>[<span data-ttu-id="13a04-130">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="13a04-130">HTTP</span></span>](#tab/http)
<!-- {"blockType": "request", "name": "remove-from-bundle" } -->

```http
DELETE https://graph.microsoft.com/beta/drive/bundles/{bundle-id}/children/{item-id}
```
# <a name="ctabcsharp"></a>[<span data-ttu-id="13a04-131">C#</span><span class="sxs-lookup"><span data-stu-id="13a04-131">C#</span></span>](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/remove-from-bundle-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javascripttabjavascript"></a>[<span data-ttu-id="13a04-132">Javascript</span><span class="sxs-lookup"><span data-stu-id="13a04-132">Javascript</span></span>](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/remove-from-bundle-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="objective-ctabobjc"></a>[<span data-ttu-id="13a04-133">目标-C</span><span class="sxs-lookup"><span data-stu-id="13a04-133">Objective-C</span></span>](#tab/objc)
[!INCLUDE [sample-code](../includes/snippets/objc/remove-from-bundle-objc-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# <a name="javatabjava"></a>[<span data-ttu-id="13a04-134">Java</span><span class="sxs-lookup"><span data-stu-id="13a04-134">Java</span></span>](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/remove-from-bundle-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### <a name="response"></a><span data-ttu-id="13a04-135">响应</span><span class="sxs-lookup"><span data-stu-id="13a04-135">Response</span></span>

<!-- { "blockType": "response" } -->

```http
HTTP/1.1 204 No Content
```


[bundle]: ../resources/bundle.md
[error-response]: /graph/errors

<!-- {
  "type": "#page.annotation",
  "description": "Remove an item from a bundle.",
  "keywords": "",
  "section": "documentation"
} -->