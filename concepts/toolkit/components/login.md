---
title: Microsoft Graph 工具包中的登录组件
description: 登录组件是一个按钮和飞出控件，可促进 Microsoft 身份平台身份验证。
localization_priority: Normal
author: nmetulev
ms.openlocfilehash: 441639c309025eb8fefbbe551dd60b6324a7fd3c
ms.sourcegitcommit: c650b95ef4d0c3e93e2eb36cd6b52ed31200164f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44682031"
---
# <a name="login-component-in-the-microsoft-graph-toolkit"></a>Microsoft Graph 工具包中的登录组件

登录组件是一个按钮和飞出控件，可促进 Microsoft 身份平台身份验证。 它提供了两种状态：
* 当用户未登录时，该控件是启动登录过程的简单按钮。
* 当用户登录时，该控件将显示当前登录的用户名、配置文件图像和电子邮件中的名称。 单击时，将打开一个带有注销命令的浮出控件。

## <a name="example"></a>示例

以下示例显示 `mgt-login` 具有已登录用户的组件。 

<iframe src="https://mgt.dev/iframe.html?id=components-mgt-login--login&source=docs" height="350"></iframe>

[在 "dev" 中打开此示例](https://mgt.dev/?path=/story/components-mgt-login--login&source=docs)

## <a name="using-the-control-without-an-authentication-provider"></a>在不使用身份验证提供程序的情况下使用控件

组件与提供程序一起使用，并在盒中使用 Microsoft Graph。 但是，如果您希望提供自己的逻辑和身份验证，则可以使用 `userDetails` 属性来设置登录用户的详细信息。 

| 属性 | 属性 | 说明 |
| --- | --- | -- |
| 用户-详细信息 | userDetails | 设置将在控件上显示的 user 对象。 |

下面的示例设置人员的详细信息。

```js
let loginControl = document.getElementById('myLoginControl');
loginControl.userDetails = {
    displayName: 'Nikola Metulev',
    mail: 'nikola@contoso.com',
    personImage: 'url'
}
```

设置 `userDetails` 为 `null` 将转到 "已注销" 状态。

使用 `loginInitiated` 和 `logoutInitiated` 事件处理登录和注销。 

## <a name="css-custom-properties"></a>CSS 自定义属性

`mgt-login`组件定义以下 CSS 自定义属性。

```css
mgt-login {
  --font-size: 14px;
  --font-weight: 600;
  --height: '100%';
  --margin: 0;
  --padding: 12px 20px;
  --color: #201f1e;
  --color-hover: var(--theme-primary-color);
  --background-color: transparent;
  --background-color--hover: #edebe9;
  --popup-content-background-color: white;
  --popup-command-font-size: 12px;
  --popup-color: #201f1e;
}
```

若要了解详细信息，请参阅[样式组件](../style.md)。

## <a name="events"></a>活动

从控件触发以下事件。

| 事件 | 说明 |
| --- | --- |
| `loginInitiated` | 用户单击了 "登录" 按钮以启动登录过程（可取消）。|
| `loginCompleted` | 登录过程成功，用户现在已登录。 |
| `loginFailed` | 用户取消了登录进程或无法登录。|
| `logoutInitiated` | 用户已开始注销。 |
| `logoutCompleted` | 用户已注销。 |

## <a name="templates"></a>模板

`mgt-login`组件支持多个[模板](../templates.md)，这些模板允许您替换组件的某些部分。 若要指定模板，请在 `<template>` 组件内添加一个元素，并将 `data-type` 值设置为下表中列出的值之一。 

| 数据类型 | 数据上下文 | Description |
| --- | --- | --- |
| 登录按钮内容 | personDetails： person 对象， `personImage` ：人员图像字符串 | 用户登录时用于呈现按钮中的内容的模板。 |
| 签出按钮-内容 | Null | 用户未登录时用于呈现按钮中的内容的模板。 |
| 浮出控件-命令 | handleSignOut：注销函数 | 用于呈现浮出控件中的命令的模板 |
| 飞出-人员-详细信息 | personDetails： person 对象，personImage： person image string | 用于在浮出控件中呈现人员详细信息的模板。 |

## <a name="microsoft-graph-permissions"></a>Microsoft Graph 权限

此组件使用 "[人员" 组件](./person.md)显示用户并继承所有权限。 

## <a name="authentication"></a>身份验证

登录控件使用[身份验证文档](./../providers.md)中介绍的全局身份验证提供程序。 

## <a name="extend-for-more-control"></a>扩展以实现更多控制

对于更复杂的方案或真正的自定义 UX，此组件将公开几种 `protected render*` 用于在组件扩展中进行重写的方法。

| 方法 | 说明 |
| - | - |
| renderButton | 呈现按钮 chrome。 |
| renderButtonContent | 呈现按钮内容。 |
| renderSignedInButtonContent | 在用户登录时呈现按钮内容。 |
| renderSignedOutButtonContent | 在用户未登录时呈现按钮内容。 |
| renderFlyout | 呈现浮出控件的镶边。 |
| renderFlyoutContent | 呈现浮出控件内容。 |
| renderFlyoutPersonDetails | 呈现飞出的人员详细信息。 |
| renderFlyoutCommands | 呈现浮出控件命令。 |

### <a name="bring-your-own-flyout"></a>引入自己的浮出控件

可以通过重写 `renderFlyout()` 方法并提供新的浮出控件，使用您自己的飞出组件来替换内置的飞入组件。

在这种情况下，请重写 `protected` 浮出控件的显示方法以更新您的替代浮出控件的可见性，以确保登录组件继续按预期方式工作。

| 方法 | 说明 |
| - | - |
| hideFlyout | 关闭浮出控件。 |
| showFlyout | 显示浮出控件。 |
| toggleFlyout | 切换浮出控件的状态。 |
