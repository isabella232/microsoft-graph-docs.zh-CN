---
title: 用户资源类型
description: 表示 Azure AD 用户帐户。继承自 directoryObject。
author: krbain
localization_priority: Priority
ms.prod: users
doc_type: resourcePageType
ms.openlocfilehash: 9e7629664c8d8ae844812d596a81a3ded716583d
ms.sourcegitcommit: 40b0e58312819b69567f35ab894ee0d2989837ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030205"
---
# <a name="user-resource-type"></a>用户资源类型

命名空间：microsoft.graph

表示 Azure AD 用户帐户。继承自 [directoryObject](directoryobject.md)。

该资源支持：

- 将你自己的数据作为[扩展](/graph/extensibility-overview)添加到自定义属性。
- 订阅[更改通知](/graph/webhooks)。
- 通过提供 [delta](../api/user-delta.md) 函数，使用 [delta 查询](/graph/delta-query-overview)跟踪增量添加、删除和更新。

## <a name="methods"></a>方法

| 方法                                                                                     | 返回类型                                                                      | 说明                                                                                                                                                                                                                         |
|:-------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [List users](../api/user-list.md)                                                          | [user](user.md) 集合                                                       | 获取用户对象列表。                                                                                                                                                                                                         |
| [Create user](../api/user-post-users.md)                                                   | [user](user.md)                                                                  | 新建用户对象。                                                                                                                                                                                                           |
| [Get user](../api/user-get.md)                                                             | [user](user.md)                                                                  | 读取 user 对象的属性和关系。                                                                                                                                                                                   |
| [Update user](../api/user-update.md)                                                       | [user](user.md)                                                                  | 更新 user 对象。                                                                                                                                                                                                                 |
| [Delete user](../api/user-delete.md)                                                       | None                                                                             | 删除 user 对象。                                                                                                                                                                                                                 |
| [获取增量](../api/user-delta.md)                                                          | [user](user.md) 集合                                                       | 获取用户的增量更改。                                                                                                                                                                                                  |
| **应用角色分配**                                                                   |                                                                                  |                                                                                                                                                                                                                                     |
| [列出 appRoleAssignments](../api/user-list-approleassignments.md)                          | [appRoleAssignment](approleassignment.md) 集合                             | 获取分配给此用户的应用和应用角色。                                                                                                                                                                       |
| [添加 appRoleAssignment](../api/user-post-approleassignments.md)                            | [appRoleAssignment](approleassignment.md)                                        | 为此用户分配应用角色。                                                                                                                                                                                                    |
| [删除应用角分配](../api/user-delete-approleassignments.md)                       | 无                                                                             | 删除分配给此用户的应用角色。                                                                                                                                                                                       |
| **Calendar**                                                                               |                                                                                  |                                                                                                                                                                                                                                     |
| [Create calendar](../api/user-post-calendars.md)                                           | [Calendar](calendar.md)                                                          | 通过发布到日历集合创建新日历。                                                                                                                                                                       |
| [Create calendarGroup](../api/user-post-calendargroups.md)                                 | [CalendarGroup](calendargroup.md)                                                | 通过发布到 calendarGroups 集合新建 CalendarGroup。                                                                                                                                                             |
| [Create event](../api/user-post-events.md)                                                 | [event](event.md)                                                                | 通过发布到事件集合新建事件。                                                                                                                                                                             |
| [findMeetingTimes](../api/user-findmeetingtimes.md)                                        | [meetingTimeSuggestionsResult](meetingtimesuggestionsresult.md)                  | 基于与会者忙闲状态、位置或时间限制查找会议时间和位置。                                                                                                                                      |
| [getSchedule](../api/calendar-getschedule.md)                                              | [scheduleInformation](scheduleinformation.md)                                    | 获取用户、通讯组列表或资源（会议室或设备）在指定时间段内的忙/闲状态信息。                                                                           |
| [List calendars](../api/user-list-calendars.md)                                            | [calendar](calendar.md) 集合                                               | 获取 Calendar 对象集合。                                                                                                                                                                                                   |
| [List calendarGroups](../api/user-list-calendargroups.md)                                  | [calendarGroup](calendargroup.md) 集合                                     | 获取 CalendarGroup 对象集合。                                                                                                                                                                                              |
| [List calendarView](../api/user-list-calendarview.md)                                      | [event](event.md) 集合                                                     | 获取 Event 对象集合。                                                                                                                                                                                                      |
| [List events](../api/user-list-events.md)                                                  | [event](event.md) 集合                                                     | 获取用户邮箱中的 event 对象列表。该列表包含单个实例会议和系列主控形状。                                                                                                                   |
| [reminderView](../api/user-reminderview.md)                                                | [Reminder](reminder.md) collection                                               | 返回指定开始时间和结束时间范围内的日历提醒列表。                                                                                                                                                       |
| **联系人**                                                                               |                                                                                  |                                                                                                                                                                                                                                     |
| [创建联系人](../api/user-post-contacts.md)                                             | [联系人](contact.md)                                                            | 通过发布到联系人集合新建联系人。                                                                                                                                                                         |
| [创建 contactFolder](../api/user-post-contactfolders.md)                                 | [contactFolder](contactfolder.md)                                                | 通过发布到 contactFolders 集合创建新 ContactFolder。                                                                                                                                                             |
| [List contacts](../api/user-list-contacts.md)                                              | [联系人](contact.md)集合                                                 | 从已登录用户的默认联系人文件夹中获取联系人集合。                                                                                                                                                    |
| [List contactFolders](../api/user-list-contactfolders.md)                                  | [ContactFolder](contactfolder.md) 集合                                     | 获取已登录用户的默认联系人文件夹中的联系人文件夹集合。                                                                                                                                             |
| **目录对象**                                                                      |                                                                                  |                                                                                                                                                                                                                                     |
| [assignLicense](../api/user-assignlicense.md)                                              | [user](user.md)                                                                  | 为用户添加或删除订阅。还可以启用和禁用与订阅相关的特定计划。                                                                                                            |
| [checkMemberGroups](../api/user-checkmembergroups.md)                                      | String collection                                                                | 检查组列表中的成员身份。检查是可传递的。                                                                                                                                                                  |
| [checkMemberObjects](../api/user-checkmemberobjects.md)                                    | String 集合                                                                | 检查组、目录角色或管理单元对象列表中的成员身份。 此函数可传递。                                                                                                                |
| [exportPersonalData](../api/user-exportpersonaldata.md)                                    | 无                                                                             | 提交公司管理员发出的数据策略操作请求，以导出组织用户的数据。                                                                                                                   |
| [getByIds](../api/directoryobject-getbyids.md)                                             | 字符串集合                                                                | 返回 ID 列表中指定的目录对象。                                                                                                                                                                           |
| [getMemberGroups](../api/user-getmembergroups.md)                                          | String collection                                                                | 返回用户是其成员的所有组。检查是可传递的。                                                                                                                                                        |
| [getMemberObjects](../api/user-getmemberobjects.md)                                        | String collection                                                                | 返回用户所属的所有组和目录角色。检查是可传递的。                                                                                                                                 |
| [List createdObjects](../api/user-list-createdobjects.md)                                  | [directoryObject](directoryobject.md) collection                                 | 从 createdObjects 导航属性中获取此用户创建的目录对象。                                                                                                                                          |
| [List licenseDetails](../api/user-list-licensedetails.md)                                  | [licenseDetails](licensedetails.md) 集合                                   | 获取 licenseDetails 对象集合。                                                                                                                                                                                             |
| [List ownedDevices](../api/user-list-owneddevices.md)                                      | [directoryObject](directoryobject.md) collection                                 | 从 ownedDevices 导航属性中获取此用户所拥有的设备。                                                                                                                                               |
| [List ownedObjects](../api/user-list-ownedobjects.md)                                      | [directoryObject](directoryobject.md) collection                                 | 从 ownedObjects 导航属性中获取此用户所拥有的目录对象。                                                                                                                                     |
| [List registeredDevices](../api/user-list-registereddevices.md)                            | [directoryObject](directoryobject.md) collection                                 | 从 registeredDevices 导航属性中获取为此用户注册的设备。                                                                                                                                    |
| [reprocessLicense](../api/user-reprocesslicenseassignment.md)                              | [user](user.md)                                                                  | 重新处理用户的订阅分配。                                                                                                                                                                                    |
| [revokeSignInSessions](../api/user-revokesigninsessions.md)                                | 无                                                                             | 通过将 **signInSessionsValidFromDateTime** 用户属性重置为当前的日期时间来吊销向应用程序发出的用户的所有刷新和会话令牌。 这将强制用户再次登录到这些应用程序。 |
| **驱动器**                                                                                  |                                                                                  |                                                                                                                                                                                                                                     |
| [获取驱动器](../api/drive-get.md)                                                           | [drive](drive.md)                                                                | 检索驱动器资源的属性和关系。                                                                                                                                                                      |
| [列出子项](../api/driveitem-list-children.md)                                         | [DriveItems](driveitem.md)                                                       | 在 DriveItem 的子项关系中返回 DriveItems 集合。                                                                                                                                                      |
| **组**                                                                                 |                                                                                  |                                                                                                                                                                                                                                     |
| [List joinedTeams](../api/user-list-joinedteams.md)                                        | [团队](team.md) 集合                                                       | 从 joinedTeams 导航属性中获取此用户直接所属的 Microsoft Teams 团队。                                                                                                                         |
| [List memberOf](../api/user-list-memberof.md)                                              | [directoryObject](directoryobject.md) collection                                 | 从 memberOf 导航属性中获取此用户是其直接成员的组和目录角色。                                                                                                                       |
| [List transitive memberOf](../api/user-list-transitivememberof.md)                         | [directoryObject](directoryobject.md) collection                                 | 列出用户所属的组和目录角色。 此操作是可传递的，并包括用户以嵌套方式所属的组。                                                                         |
| **邮件**                                                                                   |                                                                                  |                                                                                                                                                                                                                                     |
| [创建 inferenceClassificationOverride](../api/inferenceclassification-post-overrides.md) | 创建由 SMTP 地址识别的发件人的重点收件箱替代。      |                                                                                                                                                                                                                                     |
| [Create mailFolder](../api/user-post-mailfolders.md)                                       | [mailFolder](mailfolder.md)                                                      | 通过发布到 mailFolders 集合创建新 MailFolder。                                                                                                                                                                   |
| [创建邮件](../api/user-post-messages.md)                                             | [邮件](message.md)                                                            | 通过发布到邮件集合新建邮件。                                                                                                                                                                         |
| [创建 messageRule](../api/mailfolder-post-messagerules.md)                               | [messageRule](messagerule.md)                                                    | 通过指定一组条件和操作来创建 messageRule 对象。                                                                                                                                                          |
| [getMailTips](../api/user-getmailtips.md)                                                  | [邮件提醒](mailtips.md)集合                                               | 返回向已登录用户提供的一个或多个收件人的邮件提醒。                                                                                                                                                   |
| [List mailFolders](../api/user-list-mailfolders.md)                                        | [mailFolder](mailfolder.md) 集合                                           | 在已登录用户的根文件夹下获取邮件文件夹集合。                                                                                                                                                         |
| [列出邮件](../api/user-list-messages.md)                                              | [message](message.md) 集合                                                 | 获取已登录用户的邮箱中的所有邮件。                                                                                                                                                                               |
| [列出替代](../api/inferenceclassification-list-overrides.md)                         | [inferenceClassificationOverride](inferenceclassificationoverride.md) 集合 | 获取用户设置为始终以特定方式对来自特定发件人的邮件进行分类的重点收件箱替代。                                                                                                           |
| [List rules](../api/mailfolder-list-messagerules.md)                                       | [messageRule](messagerule.md) 集合                                         | 获取为用户收件箱定义的所有 messageRule 对象。                                                                                                                                                                       |
| [发送邮件](../api/user-sendmail.md)                                                       | 无                                                                             | 发送请求正文中指定的邮件。                                                                                                                                                                                     |
| **备注**                                                                                  |                                                                                  |                                                                                                                                                                                                                                     |
| [创建笔记本](../api/onenote-post-notebooks.md)                                        | [笔记本](notebook.md)                                                          | 新建 OneNote 笔记本。                                                                                                                                                                                                      |
| [列出笔记本](../api/onenote-list-notebooks.md)                                         | [notebook](notebook.md) 集合                                               | 检索 notebook 对象列表。                                                                                                                                                                                                |
| **开放扩展**                                                                        |                                                                                  |                                                                                                                                                                                                                                     |
| [创建开放扩展](../api/opentypeextension-post-opentypeextension.md)                | [openTypeExtension](opentypeextension.md)                                        | 创建开放扩展，并将自定义属性添加到新资源或现有资源。                                                                                                                                                   |
| [获取开放扩展](../api/opentypeextension-get.md)                                      | [openTypeExtension](opentypeextension.md) 集合                             | 获取扩展名称标识的开放扩展。                                                                                                                                                                             |
| **组织层次结构**                                                                          |                                                                                  |                                                                                                                                                                                                                                     |
| [分配管理器](../api/user-post-manager.md)                                              | [directoryObject](directoryobject.md)                                            | 分配用户或组织联系人，作为该用户的经理。                                                                                                                                                                  |
| [获取管理器](../api/user-list-manager.md)                                                 | [directoryObject](directoryobject.md)                                            | 从 manager 导航属性中获取是此用户的经理的用户或组织联系人。                                                                                                                            |
| [List directReports](../api/user-list-directreports.md)                                    | [directoryObject](directoryobject.md) collection                                 | 从 directReports 导航属性中获取向此用户报告的用户和联系人。                                                                                                                                      |
| **Outlook 设置**                                                                       |                                                                                  |                                                                                                                                                                                                                                     |
| [创建 Outlook 类别](../api/outlookuser-post-mastercategories.md)                     | [outlookCategory](outlookcategory.md)                                            | 在用户主类别列表中创建 outlookCategory 对象。                                                                                                                                                           |
| [获取 supportedLanguages](../api/outlookuser-supportedlanguages.md)                         | [localeInfo](localeinfo.md) 集合                                           | 获取用户支持的区域设置和语言列表，用户的邮箱服务器上配置了此信息。                                                                                                                  |
| [获取 supportedTimeZones](../api/outlookuser-supportedtimezones.md)                         | [timeZoneInformation](timezoneinformation.md collection)                         | 获取用户支持的时区列表，就像在用户的邮箱服务器上配置的那样。                                                                                                                             |
| [获取用户的邮箱设置](../api/user-get-mailboxsettings.md)                            | [mailboxSettings](mailboxsettings.md)                                            | 获取用户的 mailboxSettings。                                                                                                                                                                                                     |
| [列出 Outlook 类别](../api/outlookuser-list-mastercategories.md)                     | [outlookCategory](outlookcategory.md) 集合                                 | 获取为用户定义的所有类别。                                                                                                                                                                         |
| [转换 Exchange ID](../api/user-translateexchangeids.md)                              | [convertIdResult](convertidresult.md) 集合                                 | 对与 Outlook 相关的资源的标识符进行格式转换。                                                                                                                                                                 |
| [更新用户邮箱设置](../api/user-update-mailboxsettings.md)                      | [mailboxSettings](mailboxsettings.md)                                            | 启用、配置或禁用一个或多个用户的 mailboxSettings。                                                                                                                                                                   |
| **照片**                                                                                  |                                                                                  |                                                                                                                                                                                                                                     |
| [获取照片](../api/profilephoto-get.md)                                                    | [profilePhoto](profilephoto.md)                                                  | 获取指定的 profilePhoto 或其元数据（profilePhoto 属性）。                                                                                                                                                           |
| [更新 profilephoto](../api/profilephoto-update.md)                                       | 无                                                                             | 更新租户中任意用户的照片，其中包括已登录用户或指定的组或联系人。                                                                                                                        |
| **计划表**                                                                                |                                                                                  |                                                                                                                                                                                                                                     |
| [List tasks](../api/planneruser-list-tasks.md)                                             | [plannerTask](plannertask.md) 集合                                         | 获取分配给此用户的 plannerTasks。                                                                                                                                                                                              |
| **架构扩展**                                                                      |                                                                                  |                                                                                                                                                                                                                                     |
| [添加架构扩展值](/graph/extensibility-schema-groups)                          | 无                                                                             | 创建架构扩展定义，然后使用它向资源添加自定义键入数据。                                                                                                                                        |
| **待办任务** |||
|[创建任务](../api/todotasklist-post-tasks.md)|[todoTask](todotask.md)| 在指定的任务列表中创建 [todoTask](todotask.md)。|
|[创建任务列表](../api/todo-post-lists.md) | [todoTaskList](todotasklist.md) | 在用户的邮箱中创建微软待办任务列表。 |
|[列出任务](../api/todotasklist-list-tasks.md)|[todoTask](todotask.md) 集合|获取指定列表中的所有 [todoTask](todotask.md) 资源。|
|[列出任务列表](../api/todo-list-lists.md) | [todoTaskList](todotasklist.md) 集合 | 获取用户邮箱中的所有任务列表。 |
| **用户设置**                                                                          |                                                                                  |                                                                                                                                                                                                                                     |
| [获取设置](../api/usersettings-get.md)                                                 | [userSettings](usersettings.md)                                                  | 阅读用户和组织设置对象。                                                                                                                                                                                     |
| [更新设置](../api/usersettings-update.md)                                           | [userSettings](usersettings.md)                                                  | 更新 settings 对象的属性。                                                                                                                                                                                       |


## <a name="properties"></a>属性

| 属性       | 类型    |说明|
|:---------------|:--------|:----------|
|aboutMe|String|任意形式的文本输入字段，用于介绍用户自身。|
|accountEnabled|布尔| 启用帐户时为 **true** ，否则为 **false** 。 创建用户时此属性是必需的。 支持 `$filter`。    |
|ageGroup|String|设置用户的年龄组。 允许的值：`null`、`minor`、`notAdult` 和 `adult`。 请参阅[法定年龄组属性定义](#legal-age-group-property-definitions)以了解详细信息。 |
|assignedLicenses|[assignedLicense](assignedlicense.md) collection|分配给该用户的许可证。不可为 null。            |
|assignedPlans|[assignedPlan](assignedplan.md) collection|分配给该用户的计划。只读。不可为 null。 |
|birthday|DateTimeOffset|用户的生日。时间戳类型表示使用 ISO 8601 格式的日期和时间信息，并且始终处于 UTC 时间。例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`|
|businessPhones|String collection|用户的电话号码。注意：虽然这是字符串集合，但是只能为该属性设置一个号码。 <br>本地目录同步的用户为只读。 |
|城市|String|用户所在的城市。 支持 `$filter`。|
|companyName | String | 与用户关联的公司名称。 此属性可用于描述外部用户所属的公司。 此公司名称的最大长度为 64 个字符。<br><br>仅在 `$select` 上返回。|
|consentProvidedForMinor|String|设置是否已获得未成年人的同意。 允许的值：`null`、`granted`、`denied` 和 `notRequired`。 请参阅[法定年龄组属性定义](#legal-age-group-property-definitions)以了解详细信息。|
|country|String|用户所在的国家/地区；例如，“美国”或“英国”。 支持 `$filter`。|
|createdDateTime | DateTimeOffset |用户对象的创建日期。 |
|creationType|字符串|指示创建的用户帐户是普通学校或工作帐户 (`null`)、外部帐户 (`Invitation`)、Azure Active Directory B2C 租户的本地帐户 (`LocalAccount`) 还是使用电子邮件验证的自助注册帐户 (`EmailVerified`)。 只读。|
|deletedDateTime| DateTimeOffset | 删除用户的日期和时间。 <br><br>仅在 `$select` 上返回。 |
|department|String|用户工作部门的名称。 支持 `$filter`。|
|displayName|String|用户通讯簿中显示的名称。 这通常是用户名字、中间名首字母和姓氏的组合。 此属性在创建用户时是必需的，并且在更新过程中不能清除。 支持 `$filter` 和 `$orderby`。|
| employeeHireDate | DateTimeOffset | 聘请用户或用户将开始工作（如是未来招聘）的日期和时间。 <br><br>仅在 `$select` 上返回。 支持 `$filter`。|
| employeeId | String | 由组织分配给该用户的员工标识符。 <br><br>仅在 `$select` 上返回。 支持 `$filter`。|
|employeeOrgData|[employeeOrgData](employeeorgdata.md) |表示与用户相关联的组织数据（例如，分部和 costCenter）。 <br><br>仅在 `$select` 上返回。|
| employeeType | String | 捕获企业员工类型：员工、合同工、顾问、供应商等等。 <br><br>仅在 `$select` 上返回。 支持 `$filter`。|
|externalUserState|String|对于使用[邀请 API](../api/invitation-post.md) 邀请到租户的外部用户，此属性表示受邀用户的邀请状态。 对于受邀用户，状态可以是 `PendingAcceptance` 或 `Accepted`，而对于所有其他用户，状态为 `null`。 <br><br>仅在 `$select` 上返回。 支持包含受支持数值的`$filter`。 例如：`$filter=externalUserState eq 'PendingAcceptance'`。|
|externalUserStateChangeDateTime|DateTimeOffset|显示最近一次修改 **externalUserState** 属性的时间戳。 <br><br>仅在 `$select` 上返回。|
|faxNumber|String|用户的传真号。|
|givenName|String|用户的名。 支持 `$filter`。|
| hireDate | DateTimeOffset | 用户的雇佣日期。 时间戳类型表示采用 ISO 8601 格式的日期和时间信息，始终采用 UTC 时区。 例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`。 <br><br>仅在 `$select` 上返回。 <br><br> **注意：** 此属性特定于 SharePoint Online。 建议使用本地 **employeeHireDate** 属性来设置和更新使用 Microsoft Graph API 的聘用日期值。 |
|id|String|用户的唯一标识符。 应视为不透明的标识符。 继承自 [directoryObject](directoryobject.md)。 键。 不可为 null。 只读。|
|identities|[objectIdentity](objectIdentity.md) 集合| 表示可用于登录此用户帐户的标识。 标识可由 Microsoft （也称为本地帐户）、组织或社交身份提供商（如 Facebook、Google 和 Microsoft）提供，并绑定到用户帐户。 可能包含具有相同 **signInType** 值的多个项目。 <br>支持 `$filter`。|
|imAddresses|String collection|用户的即时消息 IP 语音 (VOIP) 会话初始协议 (SIP) 地址。只读。|
|interests|String collection|用户介绍自身兴趣的列表。|
|isResourceAccount|布尔| 请勿使用 – 保留以备今后使用。|
|jobTitle|String|用户的职务。 支持 `$filter`。|
|lastPasswordChangeDateTime| DateTimeOffset | 此 Azure AD 用户上次更改其密码的时间。 日期和时间信息采用 ISO 8601 格式，并且始终处于 UTC 时间。 例如，2014 年 1 月 1 日午夜 (UTC) 如下所示：“2014-01-01T00:00:00Z”|
|legalAgeGroupClassification|String| 由企业应用程序用于确定用户的法定年龄组。 此属性为只读状态，基于 `ageGroup` 和 `consentProvidedForMinor` 属性计算得出。 允许的值：`null`、`minorWithOutParentalConsent`、`minorWithParentalConsent`、`minorNoParentalConsentRequired`、`notAdult` 和 `adult`。 请参阅[法定年龄组属性定义](#legal-age-group-property-definitions)以了解详细信息。|
|licenseAssignmentStates|[licenseAssignmentState](licenseassignmentstate.md) 集合|此用户的许可证分配状态。 只读。|
|mail|String|用户的 SMTP 地址，例如，“jeff@contoso.onmicrosoft.com”。 支持 `$filter`。|
|mailboxSettings|[mailboxSettings](mailboxsettings.md)|已登录用户的主邮箱的设置。可以[获取](../api/user-get-mailboxsettings.md)或[更新](../api/user-update-mailboxsettings.md)用于向传入邮件发送自动答复、区域设置和时区的设置。|
|mailNickname|String|用户的邮件别名。 创建用户时必须指定此属性。 支持 `$filter`。|
|mobilePhone|String|用户的主要移动电话号码。 本地目录同步的用户为只读。 |
|mySite|String|用户个人网站的 URL。|
|officeLocation|String|用户公司地点的办公室位置。|
|onPremisesDistinguishedName|String| 包含本地 Active Directory `distinguished name` 或 `DN`。 仅当客户正在通过 Azure AD Connect 将其本地目录同步到 Azure Active Directory 时，才会填充该属性。 只读。 |
|onPremisesDomainName|String| 包含从本地目录同步的本地 `domainFQDN`（也称为 dnsDomainName）。 仅当客户正在通过 Azure AD Connect 将其本地目录同步到 Azure Active Directory 时，才会填充该属性。 只读。 |
|onPremisesExtensionAttributes|[onPremisesExtensionAttributes](onpremisesextensionattributes.md)|包含用户的 extensionAttributes 1-15。 请注意，单个扩展属性既不可选择，也不可筛选。 对于 `onPremisesSyncEnabled` 用户，这组属性集的授权来源是本地，并且为只读。 对于只使用云的用户（其中 `onPremisesSyncEnabled` 为假），可以在创建或更新期间设置这些属性。 这些扩展属性也称 Exchange 自定义属性 1-15。 |
|onPremisesImmutableId|String|此属性用于将本地 Active Directory 用户帐户关联到他们的 Azure AD 用户对象。 如果对用户的 **userPrincipalName** (UPN) 属性使用联盟域，必须在创建新用户帐户时指定此属性。 **重要说明：** 指定此属性时不能使用 **$** 和 **\_** 字符。 支持 `$filter`。                            |
|onPremisesLastSyncDateTime|DateTimeOffset|表示上一次对象与本地目录同步的时间；例如：“2013-02-16T03:04:54Z”。时间戳类型表示使用 ISO 8601 格式的日期和时间信息，并且始终处于 UTC 时间。例如，2014 年 1 月 1 日午夜 UTC 如下所示：`'2014-01-01T00:00:00Z'`。只读。|
|onPremisesProvisioningErrors|[onPremisesProvisioningError](onpremisesprovisioningerror.md) 集合| 在预配期间使用 Microsoft 同步产品时发生的错误。 |
|onPremisesSamAccountName|String| 包含从本地目录同步的本地 `samAccountName`。 仅当客户正在通过 Azure AD Connect 将其本地目录同步到 Azure Active Directory 时，才会填充该属性。 只读。 |
|onPremisesSecurityIdentifier|String|包含从本地同步到云的用户的本地安全标识符 (SID)。只读。|
|onPremisesSyncEnabled|Boolean| 如果此对象从本地目录同步，则为 **true** ；如果此对象最初从本地目录同步，但以后不再同步，则为 **false** ；如果此对象从未从本地目录同步，则为 **null** （默认值）。只读 |
|onPremisesUserPrincipalName|String| 包含从本地目录同步的本地 `userPrincipalName`。 仅当客户正在通过 Azure AD Connect 将其本地目录同步到 Azure Active Directory 时，才会填充该属性。 只读。 |
|otherMails|字符串集合| 用户的其他电子邮件地址列表；例如：`["bob@contoso.com", "Robert@fabrikam.com"]`。 支持 $filter。|
|passwordPolicies|String|指定用户的密码策略。此值是一个枚举，具有一个可能值“DisableStrongPassword”，允许指定比默认策略弱的密码。还可以指定“DisablePasswordExpiration”。可以同时指定这两个策略；例如：“DisablePasswordExpiration、DisableStrongPassword”。|
|passwordProfile|[passwordProfile](passwordprofile.md)|指定用户的密码配置文件。配置文件包含用户的密码。创建用户时此属性是必需的。配置文件中的密码必须满足 **passwordPolicies** 属性指定的最低要求。默认情况下，必须使用强密码。|
|pastProjects|String collection|供用户枚举其过去项目的列表。|
|postalCode|String|用户邮政地址的邮政编码。邮政编码特定于用户所在的国家/地区。在美国，此属性包含邮政编码。|
|preferredLanguage|String|用户的首选语言。应遵循 ISO 639-1 代码；例如“EN-US”。|
|preferredName|String|用户的首选名称。|
|provisionedPlans|[provisionedPlan](provisionedplan.md) 集合|为用户设置的计划。只读。不可为 null。 |
|proxyAddresses|String 集合|示例：`["SMTP: bob@contoso.com", "smtp: bob@sales.contoso.com"]` 多值属性筛选器表达式需要 **any** 运算符。 只读，不可为 Null。 支持 `$filter`。|
|refreshTokensValidFromDateTime|DateTimeOffset|在此时间之前发出的任何刷新令牌或会话令牌（会话 Cookie）都是无效的，并且当使用无效的刷新令牌或会话令牌获取委托的访问令牌（用于访问 Microsoft Graph 等 API）时，应用程序将收到错误。  如果发生这种情况，应用程序将需要通过向授权端点发出请求来获取新的刷新令牌。 <br><br>仅在 `$select` 上返回。 只读。 |
|responsibilities|String collection|供用户枚举其职责的列表。|
|schools|String collection|供用户枚举其学习过的学校列表。|
|showInAddressList|Boolean|如果 Outlook 全局地址列表应包含此用户，则值为 **true** ，否则为 **false** 。 如果未设置，则将其视为 **true** 。 对于通过邀请管理器邀请的用户，此属性将设置为 **false** 。|
|skills|String collection|供用户枚举其技能的列表。|
|signInSessionsValidFromDateTime|DateTimeOffset| 在此时间之前发出的任何刷新令牌或会话令牌（会话 Cookie）都是无效的，并且当使用无效的刷新令牌或会话令牌获取委托的访问令牌（用于访问 Microsoft Graph 等 API）时，应用程序将收到错误。  如果发生这种情况，应用程序将需要通过向授权端点发出请求来获取新的刷新令牌。 此为只读属性。 使用 [revokeSignInSessions](../api/user-revokesigninsessions.md) 进行重置。|
|state|String|用户地址中的省/市/自治区或省。 支持 `$filter`。|
|streetAddress|String|用户公司地点的街道地址。|
|surname|String|用户的姓氏。 支持 `$filter`。|
|usageLocation|String|两个字母的国家/地区代码（ISO 标准 3166）。 为检查服务在国家/地区的可用性，这对根据法律要求将分配许可证的用户而言是必需的。  示例包括：“US”、“JP”和“GB”。 不可为 null。 支持 `$filter`。|
|userPrincipalName|String|用户的用户主体名称 (UPN)。 UPN 是用户基于 Internet 标准 RFC 822 的 Internet 式登录名。 按照惯例，此名称应映射到用户的电子邮件名称。 常规格式是 alias@domain，其中 domain 必须位于租户的已验证域集合中。 创建用户时此属性是必需的。 可从 [组织](organization.md) 的 **verifiedDomains** 属性访问租户的已验证域。 支持 `$filter` 和 `$orderby`。
|userType|String|可用于对目录中的用户类型分类的字符串值，例如“成员”和“访客”。 支持 `$filter`。          |

### <a name="legal-age-group-property-definitions"></a>法定年龄组属性定义

本部分介绍 Azure AD 管理员和企业应用程序开发人员如何使用三个法定年龄组属性（`legalAgeGroupClassification`、`ageGroup` 和 `consentProvidedForMinor`）来满足与年龄相关的法规。

例如：Cameron 是英国 Holyport 小学的名录管理员。 新学年开始，他根据英国与年龄相关的法规，使用入学文件获得未成年人父母的同意。 征得父母同意后，Holyport 学校和 Microsoft 应用可以使用未成年人的帐户。 Cameron 随后创建所有帐户，将 ageGroup 设置为“minor”，并将 consentProvidedForMinor 设置为“granted”。 然后，他的学生使用的应用程序可以禁止不适合未成年人的功能。

#### <a name="legal-age-group-classification"></a>法定年龄组分类

企业应用程序开发人员使用此只读属性来确保根据用户的法定年龄组正确处理用户。 此属性是基于用户的 `ageGroup` 和 `consentProvidedForMinor` 属性计算得出的。

| 值    | #  |说明|
|:---------------|:--------|:----------|
|空|0|默认值，尚未给用户设置 `ageGroup`。|
|minorWithoutParentalConsent |1|（保留以备今后使用）|
|minorWithParentalConsent|2| 根据用户所在国家或地区与年龄相关的法规，将用户视为未成年人，并且帐户管理员已相应获得父母或监护人的同意。|
|adult|3|根据用户所在国家或地区与年龄相关的法规，将用户视为成年人。|
|notAdult|4|用户所在国家或地区存在其他与年龄相关的法规（例如美国、英国、欧盟和韩国），用户的年龄介于未成年人和成年人之间（根据所在国家或地区的规定）。 通常，这意味着会在管控的国家或地区将青少年视为 `notAdult`。|
|minorNoParentalConsentRequired|5|用户是未成年人，但所在国家或地区没有与年龄相关的法规。|

#### <a name="age-group-and-minor-consent"></a>年龄组和未成年人同意

年龄组和未成年人同意属性是 Azure AD 管理员使用的可选属性，可帮助确保根据用户所在国家或地区与年龄相关的监管规则正确处理帐户的使用。

#### <a name="agegroup-property"></a>ageGroup 属性

| 值    | #  |说明|
|:---------------|:--------|:----------|
|空|0|默认值，尚未给用户设置 `ageGroup`。|
|minor|1|该用户被视为未成年人。|
|notAdult|2|用户所在国家或地区存在其他法规（例如美国、英国、欧盟和韩国），而且用户年龄超过儿童年龄上限（根据所在国家或地区的规定）且低于成年人年龄下限（根据所在国家或地区的规定）。 因此，基本上会在管控的国家或地区将青少年视为 `notAdult`。|
|adult|3|应将用户视为成年人。|

#### <a name="consentprovidedforminor-property"></a>consentProvidedForMinor 属性

| 值    | #  |说明|
|:---------------|:--------|:----------|
|空|0|默认值，尚未给用户设置 `consentProvidedForMinor`。|
|granted|1|已就用户拥有帐户获得同意。|
|denied|2|尚未就用户拥有帐户获得同意。|
|notRequired|3|用户所在地不要求获得同意。|

## <a name="relationships"></a>关系

| 关系 | 类型    |说明|
|:---------------|:--------|:----------|
|activities|[userActivity](projectrome-activity.md) 集合|跨设备的用户活动。 只读。 可为 Null。|
|calendar|[calendar](calendar.md)|用户的主日历。只读。|
|calendarGroups|[CalendarGroup](calendargroup.md) 集合|用户的日历组。只读。可为 Null。|
|calendarView|[event](event.md) 集合|日历的日历视图。只读。可为 Null。|
|calendars|[calendar](calendar.md) 集合|用户的日历。只读。可为 Null。|
|contactFolders|[ContactFolder](contactfolder.md) 集合|用户的联系人文件夹。只读。可为 Null。|
|contacts|[contact](contact.md) 集合|用户的联系人。只读。可为 Null。|
|createdObjects|[directoryObject](directoryobject.md) collection|由用户创建的 directory 对象。只读。可为 Null。|
|directReports|[directoryObject](directoryobject.md) collection|向此用户报告的用户和联系人。（其 manager 属性已设置为此用户的用户和联系人。）只读。可为 Null。 |
|drive|[drive](drive.md)|用户的 OneDrive。只读。|
|drives|[drive](drive.md) 集合| 该用户的可用驱动器集合。只读。 |
|活动|[event](event.md) 集合|用户的事件。默认显示“默认日历”下的事件。只读。可为 Null。|
|extensions|[扩展](extension.md)集合|为用户定义的开放扩展集合。只读。可为 Null。|
|inferenceClassification | [inferenceClassification](inferenceclassification.md) | 基于显式指定的用户邮件的相关性分类，可以替代推断的相关性或重要性。 |
|insights|[officeGraphInsights](officegraphinsights.md) | 只读。可为空。|
|licenseDetails|[licenseDetails](licensedetails.md) 集合|此用户许可证详细信息的集合。 只读。|
|mailFolders|[mailFolder](mailfolder.md) 集合| 用户的邮件文件夹。只读。可为 Null。|
|manager|[directoryObject](directoryobject.md)|是此用户的经理的用户或联系人。 只读。 （HTTP 方法：GET、PUT、DELETE）|
|memberOf|[directoryObject](directoryobject.md) collection|用户所属的组和目录角色。只读。可为 Null。|
|messages|[message](message.md) 集合|邮箱或文件夹中的邮件。只读。可为 Null。|
|onenote|[onenote](onenote.md)| 只读。|
|outlook|[outlookUser](outlookuser.md)| 只读。|
|ownedDevices|[directoryObject](directoryobject.md) collection|用户拥有的设备。只读。可为 Null。|
|ownedObjects|[directoryObject](directoryobject.md) collection|用户拥有的 directory 对象。只读。可为 Null。|
|people|[person](person.md) 集合| 与用户相关的人员。 只读。 可为 Null。
|photo|[profilePhoto](profilephoto.md)| 用户的个人资料照片。只读。|
|planner|[plannerUser](planneruser.md)| 用户可能存在的 Planner 资源入口点。 只读。|
|registeredDevices|[directoryObject](directoryobject.md) collection|已注册的用户的设备。只读。可为 Null。|
|todo|[todo](todo.md)|表示用户可以使用的微软待办服务。 |

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!--{
  "blockType": "resource",
  "baseType": "microsoft.graph.directoryObject",
  "openType": true,
  "optionalProperties": [
    "appRoleAssignments",
    "calendar",
    "calendarGroups",
    "calendarView",
    "calendars",
    "contactFolders",
    "contacts",
    "createdObjects",
    "directReports",
    "drive",
    "events",
    "extensions",
    "joinedGroups",
    "mailFolders",
    "manager",
    "memberOf",
    "messages",
    "oauth2PermissionGrants",
    "onenote",
    "ownedDevices",
    "ownedObjects",
    "photo",
    "registeredDevices"
  ],
  "@odata.type": "microsoft.graph.user",
  "@odata.annotations": [
    {
      "capabilities": {
        "changeTracking": true
      }
    },
    {
      "property": "calendar",
      "capabilities": {
        "changeTracking": false,
        "deletable": false,
        "expandable": false,
        "insertable": false,
        "searchable": false,
        "updatable": false
      }
    },
    {
      "property": "calendarGroups",
      "capabilities": {
        "changeTracking": false,
        "expandable": false,
        "searchable": false
      }
    },
    {
      "property": "calendars",
      "capabilities": {
        "changeTracking": false,
        "expandable": false,
        "searchable": false
      }
    },
    {
      "property": "calendarView",
      "capabilities": {
        "changeTracking": true,
        "deletable": false,
        "expandable": true,
        "insertable": false,
        "navigability": "single",
        "searchable": false,
        "updatable": false
      }
    },
    {
      "property": "contactFolders",
      "capabilities": {
        "changeTracking": true,
        "expandable": false,
        "searchable": false
      }
    },
    {
      "property": "contacts",
      "capabilities": {
        "changeTracking": true,
        "expandable": false
      }
    },
    {
      "property": "events",
      "capabilities": {
        "changeTracking": false,
        "expandable": false,
        "searchable": false
      }
    },
    {
      "property": "inferenceClassification",
      "capabilities": {
        "changeTracking": false,
        "deletable": false,
        "expandable": false,
        "insertable": false,
        "searchable": false
      }
    },
    {
      "property": "mailFolders",
      "capabilities": {
        "changeTracking": true,
        "expandable": false,
        "searchable": false
      }
    },
    {
      "property": "messages",
      "capabilities": {
        "changeTracking": false,
        "expandable": false
      }
    },
    {
      "property": "people",
      "capabilities": {
        "changeTracking": false,
        "deletable": false,
        "expandable": false,
        "insertable": false,
        "updatable": false
      }
    },
    {
      "property": "photo",
      "capabilities": {
        "changeTracking": false,
        "deletable": false,
        "expandable": false,
        "insertable": false,
        "searchable": false
      }
    },
    {
      "property": "photos",
      "capabilities": {
        "changeTracking": false,
        "deletable": false,
        "expandable": false,
        "insertable": false,
        "searchable": false,
        "updatable": false
      }
    }
  ]
}-->

```json
{
  "aboutMe": "string",
  "accountEnabled": true,
  "ageGroup": "string",
  "assignedLicenses": [{"@odata.type": "microsoft.graph.assignedLicense"}],
  "assignedPlans": [{"@odata.type": "microsoft.graph.assignedPlan"}],
  "birthday": "String (timestamp)",
  "businessPhones": ["string"],
  "city": "string",
  "companyName": "string",
  "consentProvidedForMinor": "string",
  "country": "string",
  "createdDateTime": "String (timestamp)",
  "creationType": "string",
  "department": "string",
  "displayName": "string",
  "employeeHireDate": "2020-01-01T00:00:00Z",
  "employeeId": "string",
  "employeeOrgData": {"@odata.type": "microsoft.graph.employeeOrgData"},
  "employeeType": "string",
  "faxNumber" : "string",
  "givenName": "string",
  "hireDate": "String (timestamp)",
  "id": "string (identifier)",
  "identities": [{"@odata.type": "microsoft.graph.objectIdentity"}],
  "imAddresses": ["string"],
  "interests": ["string"],
  "isResourceAccount": false,
  "jobTitle": "string",
  "legalAgeGroupClassification": "string",
  "licenseAssignmentStates": [{"@odata.type": "microsoft.graph.licenseAssignmentState"}],
  "lastPasswordChangeDateTime": "String (timestamp)",
  "mail": "string",
  "mailboxSettings": {"@odata.type": "microsoft.graph.mailboxSettings"},
  "mailNickname": "string",
  "mobilePhone": "string",
  "mySite": "string",
  "officeLocation": "string",
  "onPremisesDistinguishedName": "string",
  "onPremisesDomainName": "string",
  "onPremisesExtensionAttributes": {"@odata.type": "microsoft.graph.onPremisesExtensionAttributes"},
  "onPremisesImmutableId": "string",
  "onPremisesLastSyncDateTime": "String (timestamp)",
  "onPremisesProvisioningErrors": [{"@odata.type": "microsoft.graph.onPremisesProvisioningError"}],
  "onPremisesSamAccountName": "string",
  "onPremisesSecurityIdentifier": "string",
  "onPremisesSyncEnabled": true,
  "onPremisesUserPrincipalName": "string",
  "otherMails": ["string"],
  "passwordPolicies": "string",
  "passwordProfile": {"@odata.type": "microsoft.graph.passwordProfile"},
  "pastProjects": ["string"],
  "postalCode": "string",
  "preferredLanguage": "string",
  "preferredName": "string",
  "provisionedPlans": [{"@odata.type": "microsoft.graph.provisionedPlan"}],
  "proxyAddresses": ["string"],
  "responsibilities": ["string"],
  "schools": ["string"],
  "showInAddressList": true,
  "signInSessionsValidFromDateTime": "String (timestamp)",
  "skills": ["string"],
  "state": "string",
  "streetAddress": "string",
  "surname": "string",
  "usageLocation": "string",
  "userPrincipalName": "string",
  "userType": "string",

  "calendar": { "@odata.type": "microsoft.graph.calendar" },
  "calendarGroups": [{ "@odata.type": "microsoft.graph.calendarGroup" }],
  "calendarView": [{ "@odata.type": "microsoft.graph.event" }],
  "calendars": [ {"@odata.type": "microsoft.graph.calendar"} ],
  "contacts": [ { "@odata.type": "microsoft.graph.contact" } ],
  "contactFolders": [ { "@odata.type": "microsoft.graph.contactFolder" } ],
  "createdObjects": [ { "@odata.type": "microsoft.graph.directoryObject" } ],
  "directReports": [ { "@odata.type": "microsoft.graph.directoryObject" } ],
  "drive": { "@odata.type": "microsoft.graph.drive" },
  "drives": [ { "@odata.type": "microsoft.graph.drive" } ],
  "events": [ { "@odata.type": "microsoft.graph.event" } ],
  "inferenceClassification": { "@odata.type": "microsoft.graph.inferenceClassification" },
  "mailFolders": [ { "@odata.type": "microsoft.graph.mailFolder" } ],
  "manager": { "@odata.type": "microsoft.graph.directoryObject" },
  "memberOf": [ { "@odata.type": "microsoft.graph.directoryObject" } ],
  "messages": [ { "@odata.type": "microsoft.graph.message" } ],
  "outlook": { "@odata.type": "microsoft.graph.outlookUser" },
  "ownedDevices": [ { "@odata.type": "microsoft.graph.directoryObject" } ],
  "ownedObjects": [ { "@odata.type": "microsoft.graph.directoryObject" } ],
  "photo": { "@odata.type": "microsoft.graph.profilePhoto" },
  "registeredDevices": [ { "@odata.type": "microsoft.graph.directoryObject" } ]
}

```

## <a name="see-also"></a>另请参阅

- [使用扩展向资源添加自定义数据](/graph/extensibility-overview)
- [使用开放扩展向用户添加自定义数据](/graph/extensibility-open-users)
- [使用架构扩展向组添加自定义数据](/graph/extensibility-schema-groups)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "user resource",
  "keywords": "",
  "suppressions" : [
     "Warning: /api-reference/v1.0/resources/user.md/microsoft.graph.user:
      Property 'createdDateTime' found in markdown table but not in resource definition."
  ],
  "section": "documentation",
  "tocPath": ""
}-->

