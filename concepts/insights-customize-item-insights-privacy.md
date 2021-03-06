---
title: 自定义 Microsoft Graph 中的项目见解隐私
description: ''
author: simonhult
localization_priority: Priority
ms.prod: insights
ms.custom: scenarios:getting-started
ms.openlocfilehash: 7a2e587692f5e1eb54d46887c46b00d0ca5692ce
ms.sourcegitcommit: 60ced1be6ed8dd2d23263090a1cfbc16689bb043
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48782425"
---
# <a name="customizing-item-insights-privacy-in-microsoft-graph-preview"></a>自定义 Microsoft Graph 中的项目见解隐私（预览版）

项目见解隐私设置提供了在用户与 Microsoft 365 中其他项目（例如文档或站点）之间，对派生自 Microsoft Graph 见解的可见性进行配置的能力。 可通过预先存在的控件禁用 Delve 应用，但允许其他基于见解的体验，以继续提供协助。

## <a name="background"></a>背景
2014 年首次发布时，Office Graph 是 Delve 的后端服务。 它们为 Office Graph 见解和 Delve 用户界面共享了一组数据保护控件。 此后，作为每个 Microsoft 365 体验和 Microsoft Graph 的一部分，Office Graph 不断发展并变得更加独立和强大。 为了提供一致的 Microsoft Graph 架构，Microsoft引入了一个 [itemInsights](/graph/api/resources/iteminsights?view=graph-rest-beta&preserve-view=true)实体，其继承了先前存在的 [officeGraphInsights](/graph/api/resources/officegraphinsights?view=graph-rest-beta&preserve-view=true)资源的所有属性，并保留了 **officeGraphInsights** ，以向后兼容。 **itemInsights** 的引入还使两个独立作品的隐私故事分离。  

虽然现有应用可以继续使用 **officeGraphInsights** ，但这些应用应升级到 **itemInsights** ，以获得在 Office Graph 和 Delve 中微调项目见解的灵活性。

## <a name="how-to-customize-item-insights"></a>如何自定义项目见解？

项目见解设置为管理员提供了使用 Azure AD 工具的灵活性。 管理员可为整个组织禁用项目见解，也可以仅针对指定 Azure AD 组的成员禁用项目见解。 使用 PowerShell SDK 或 Microsoft Graph REST API 通过应有权限来配置项目见解。 注意，该操作需要 _全局管理员角色_ 。 

下一部分介绍了如何使用 PowerShell cmdlet 来配置见解设置。 如果你使用的是 REST API，请跳过下一部分，继续[使用 REST API 配置项目见解](#configure-item-insights-using-rest-api)。 有关详细信息，请参阅 [read](/graph/api/iteminsightssettings-get?view=graph-rest-beta&preserve-view=true) 或 [update](/graph/api/iteminsightssettings-update?view=graph-rest-beta&preserve-view=true) REST 操作。

### <a name="how-to-configure-item-insights-setting-via-powershell"></a>如何通过 PowerShell 配置项目见解设置？
确认以下附加先决条件。 然后，你可以使用 [Microsoft Graph PowerShell SDK](/graph/powershell/installation) 为整个组织或特定组设置项目见解。

#### <a name="additional-prerequisites"></a>附加先决条件
* **PowerShell 模块** - 安装[模块 0.9.1 或更高版本](https://www.powershellgallery.com/packages/Microsoft.Graph)。
* **.NET Framework** - 安装 [.NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework) 或更高版本。

#### <a name="command-examples"></a>命令示例
若要获取组织的项目见解配置，请使用 Microsoft Graph PowerShell 模块和以下命令（在其中将 `$OrgID` 替换为适用的 ID 组织）：
```powershell
   Get-MgOrganizationSettingItemInsight -OrganizationId $OrgID
```

默认情况下，将为整个组织启用项目见解。 你可以使用 Microsoft Graph PowerShell 模块来更改该设置并为组织中的所有人禁用项目见解。 请使用以下命令（在其中将 `$OrgID` 替换为你的组织 ID 并将 `-IsEnabledInOrganization` 指定为 `false`）：
```powershell
   Update-MgOrganizationSettingItemInsight -OrganizationId $OrgID -IsEnabledInOrganization:$false
```
或者，你也可以更改默认设置并为特定 Azure AD 组禁用项目见解。 请使用以下命令（在其中将 `$OrgID` 替换为你的组织 ID 并将 `$GroupID` 替换为 Azure AD 组 ID）：
```powershell
   Update-MgOrganizationSettingItemInsight -OrganizationId $OrgID -DisabledForGroup $GroupId
```

#### <a name="using-earlier-versions-of-the-powershell-module"></a>使用早期版本的 PowerShell 模块

如果你使用的是 Microsoft Graph PowerShell 模块的 0.9.0 版或更低版本，请使用以下两种方法之一来调用 `Update-MgOrganizationSettingItemInsight` cmdlet，如以下示例所示： 

- 将 `-AdditionalProperties @{}` 添加到命令结尾：
  ```powershell
  Update-MgOrganizationSettingItemInsight -OrganizationId $OrgID -DisabledForGroup 28f9ceac-39aa-4829-9a67-b8f1db11eaa1 -AdditionalProperties @{}
  ```
- 或使用 `-BodyParameter`： 
  ```powershell
  Update-MgOrganizationSettingItemInsight -OrganizationId $OrgID -BodyParameter @{DisabledForGroup = "85f741b4-e924-41a8-abf8-d61a7b950bb5"; IsEnabledInOrganization = $false}
  ```

### <a name="configure-item-insights-using-rest-api"></a>使用 REST API 配置项目见解
如前所述，默认情况下，将为整个组织启用项目见解隐私设置。 可采用以下两种方式之一来更改默认设置：

- 为组织中的所有用户禁用项目见解：将 [itemInsightsSettings](/graph/api/resources/iteminsightssettings?view=graph-rest-beta&preserve-view=true) 资源的 **isEnabledInOrganization** 属性设置为 `false`。 
- 为用户的 _子集_ 禁用项目见解：将这些用户分配到一个 Azure AD 组中，将 **disabledForGroup** 属性设置为该组的 ID。 详细了解如何[创建组并将用户添加为成员](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)。 

使用 [update](/graph/api/iteminsightssettings-update?view=graph-rest-beta&preserve-view=true) 操作来相应地设置 **isEnabledInOrganization** 和 **disabledForGroup** 属性。

| 如何启用项目见解 | isEnabledInOrganization | disabledForGroup |
|:-------------|:------------|:------------|
| 整个组织（默认） | `true` | 空 |
| 组织用户子集禁用 | `true` | 包含用户子集的 Azure AD 组 ID |
| 整个组织禁用 | `false` | 忽略 |

更新项目见解设置时，请记住以下几点：
- [项目见解设置](/graph/api/resources/iteminsightssettings?view=graph-rest-beta&preserve-view=true)仅可用于 beta 版终结点。
- 从 Azure 门户获取 Azure AD 组 ID，并确保该组存在，因为更新操作不会检查组是否存在。 在 **disabledForGroup** 中指定不存在的组 _不会_ 禁用组织中任何用户的见解。
- 更新设置最多可能需要 8 个小时才能应用到所有 Microsoft 365 体验中。
- 无论项目见解设置如何，Delve 都会继续采用 Delve 租户和用户级别的[隐私设置](/sharepoint/delve-for-office-365-admins#control-access-to-delve-and-related-features?view=graph-rest-beta&preserve-view=true)。


## <a name="behavior-changes-in-ui-and-apis"></a>UI 和 API 中的行为更改
某些[趋势](/graph/api/resources/insights-trending)或[已使用](/graph/api/resources/insights-used)的见解可能会受到影响，如下所述。 随着时间推移，这些见解的范围和类型将得到扩展。 

- 对于禁用项目见解的用户，个人资料卡不会显示其 **使用过的** 文档。 相同的限制适用于 Microsoft 必应搜索的配置文件结果，其中“ **最近文件** ”窗格为空。 此外，降低了首字母缩写词扩展搜索精度。

- 在 Delve 中，禁用项目见解的用户将其文档隐藏。 

- 禁用项目见解的任何用户的活动都将从组织范围的见解中删除。 通常，此类分析会为用户的同事提供从 Outlook 到 OneDrive 和 SharePoint 的多种体验的辅助见解。 无论设置如何，分析始终是匿名的，但是当用户禁用见解时，该用户的活动将无法提高其他人的工作效率。

- 对于已禁用项目见解的用户，在 Microsoft Graph API 中查询[趋势](/graph/api/resources/insights-trending)和[已使用](/graph/api/resources/insights-used)资源将返回 `HTTP 403 Forbidden`。

- 如果已为在 Outlook 移动版中进行搜索的用户启用 **发现** 部分，当为该用户禁用项目见解时，会在 **发现** 部分隐藏该用户常用的文档。 否则，将基于该用户的其他活动来推荐和显示常用文档。


## <a name="transition-period"></a>过渡期
为了适应配置项目见解设置，到 2020年底，Microsoft 365 采用 Delve 设置和项目见解设置，并且如果两者有所不同，则将两者严格化。 这意味着，如果用户通过 Delve 控件或项目见解设置选择退出，则认为用户已退出项目见解。

在此过渡期后，Delve 设置仅控制 Delve 体验，并且项目见解设置仅影响 Microsoft Graph 项目见解。 确保根据组织的要求配置项目见解。


> [!NOTE]
> 过渡期间，由于技术原因，如果组织为所有用户禁用项目见解，则 SharePoint 起始页可能会提供过时的建议。 此问题将在未来的服务器端更改中得到解决。 

## <a name="see-also"></a>另请参阅
了解 Delve 以及如何使用 Delve 功能设置来控制在 **发现** 源中显示的文档： 
- [在 Office Delve 中连接和协作](https://support.microsoft.com/office/connect-and-collaborate-in-office-delve-46f92806-b52c-4187-b60e-b3bf8d25f73e)
- [我的文档在 Office Delve 中安全吗？](https://support.microsoft.com/office/are-my-documents-safe-in-office-delve-f5f409a2-37ed-4452-8f61-681e5e1836f3)
- [面向管理员的 Delve](/sharepoint/delve-for-office-365-admins)
