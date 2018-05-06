---
title: Microsoft Flow GDPR 数据主体删除请求 | Microsoft Docs
description: 了解如何使用 Microsoft Flow 来响应 GPDR 数据主体删除请求。
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: d750ee2bc672d08bff940341349663b4721f9a57
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>响应 Microsoft Flow 的 GDPR 数据主体删除请求

从组织的客户数据中删除个人数据的“删除权限”是 GDPR 中的关键保护。 删除个人数据包括删除所有个人数据和系统生成的日志，但审核日志信息除外。

Microsoft Flow 允许用户生成自动化工作流，它是组织日常操作的关键部分。 当用户离开组织时，管理员需要手动检查并确定是否删除由该用户创建的某些数据和资源。 从 Azure Active Directory 删除用户帐户时，将自动删除其他个人数据。

下表显示了哪些个人数据将自动删除，以及哪些数据需要管理员手动检查和删除：

|需手动检查和删除|从 Azure Active Directory 删除用户时自动删除|
|------|------|
|环境*|系统生成的日志|
|环境权限**|运行历史记录|
|流|用户作业|
|流权限|网关 |
|用户详细信息|网关权限 |
|连接*||
|连接权限||
|自定义连接器*||
|自定义连接器权限||

* 每个资源都包含带个人数据的“创建者”和“修改者”记录。 出于安全原因，将保留这些记录直至删除资源。

* 对于包含 Common Data Service For Apps 数据库的环境，环境权限（例如，向用户分配的“环境创建者”和“管理员”角色）将存储为 Common Data Service 数据库中的记录。 有关如何对使用 Common Data Service 的用户的 DSR 进行响应的指导，请参阅[针对 Common Data Service 客户数据执行 DSR](https://go.microsoft.com/fwlink/?linkid=872251)。

对于需要进行手动检查的数据和资源，Microsoft Flow 提供了以下经验，以便查找或更改特定用户的个人数据：

* Website 访问：登录到 [PowerApps 管理中心](https://admin.powerapps.com/)或 [Microsoft Flow 管理中心](https://admin.flow.microsoft.com/)

* PowerShell 访问：[PowerApps Admin PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804) 

以下是管理员可以在每种类型的资源中删除各类型个人数据的经验细分：

|包含个人数据的资源|网站访问|PowerShell 访问|自动删除|
|-----|----|----|----|
|系统生成的日志|[Office 365 服务信任门户](https://servicetrust.microsoft.com/)|||
|环境|Microsoft Flow 管理中心|PowerApps cmdlet||
|环境权限*|Microsoft Flow 管理中心|PowerApps cmdlet||
|运行历史记录||| 通过 28 天保留策略删除|
|活动源 ||PowerApps cmdlet||
|用户作业|| ||
|流|Microsoft Flow Maker 门户**|||
|流权限|Microsoft Flow Maker 门户|||
|用户详细信息|| ||
|连接|Microsoft Flow Maker 门户| ||
|连接权限|Microsoft Flow Maker 门户| ||
|自定义连接器|Microsoft Flow Maker 门户| ||
|自定义连接器权限|Microsoft Flow Maker 门户| ||
|审批历史记录|Microsoft PowerApps Maker 门户*|||

*随着 Common Data Service for Apps 的推出，如果在环境中创建一个数据库，环境权限和模型驱动应用权限将作为记录存储在 Common Data Service for Apps 数据库实例中。 有关如何对使用 Common Data Service 的用户的 DSR 进行响应的指导，请参阅[针对 Common Data Service 客户数据执行 DSR](https://go.microsoft.com/fwlink/?linkid=872251)。

** 如果管理员已获得 Microsoft Flow 管理中心的访问权限，管理员将只能从 Microsoft Flow Maker 门户访问这些资源。

## <a name="manage-delete-requests"></a>管理删除请求

下面的步骤介绍了如何使用管理功能为 GDPR 的删除请求提供服务。

> [!IMPORTANT]
> 若要避免数据损坏，请按顺序执行这些步骤。
>
>

## <a name="list-and-re-assign-flows"></a>列出并重新分配流

这些步骤将复制即将离开用户的现有流。 如果将新的所有权分配到副本，这些流可以继续支持现有的业务流程。 复制这些流对于删除即将离开的用户的个人标识符链接至关重要，必须为流建立新的连接以连接其他 API 和 SaaS 应用程序。

1. 登录到 [Microsoft Flow 管理中心](https://admin.flow.microsoft.com/)，然后选择包含已删除用户所拥有流的环境。

    ![查看环境](./media/gdpr-dsr-delete/view-environments.png)

1. 选择“资源”>“流”，然后选择想要重新分配的流标题。

    ![查看流](./media/gdpr-dsr-delete/admin-view-flows.png)

1. 选择“管理共享”。

    ![管理共享](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. 在右边缘附近显示的“共享”面板中，将你自己添加为所有者，然后选择“保存”。

    ![共享流](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. 登录到 [Microsoft Flow](https://flow.microsoft.com/)，选择“我的流”，然后选择“团队流”。

1. 选择要复制的流的省略号 (...)，然后选择“另存为”。

    ![流另存为](./media/gdpr-dsr-delete/flow-save-as.png)

1. 根据需要配置连接，然后选择“继续”。

1. 提供新名称，然后选择“保存”。

    ![创建流副本](./media/gdpr-dsr-delete/create-copy-flow.png)

1. 此新版本流显示在“我的流”中，可以在其中与其他用户共享（如果需要）。

    ![团队流](./media/gdpr-dsr-delete/team-flows.png)

1. 若要删除原始流，请依次选择相应的省略号 (…)、“删除”，并在再次出现提示时选择“删除”。 此步骤还将删除用户和 Microsoft Flow 之间系统依赖关系中包含的基础个人标识符。

    ![确认删除流](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. 若要启用流副本，打开“我的流”，然后将“切换”控件切换为“启用”。
    ![启用流](./media/gdpr-dsr-delete/toggle-on.png)

1. 副本现在将执行与原始版本相同的工作流逻辑。

## <a name="delete-approval-history-from-microsoft-flow"></a>从 Microsoft Flow 删除审批历史记录

 Microsoft Flow 审批数据存储在 Common Data Service for Apps 的当前版本或以前版本中。 在审批中，个人信息以审批分配以及包含在审批响应中的注释形式存在。 管理员可以通过执行以下步骤访问该数据：

1. 登录到 [PowerApps](https://web.powerapps.com/)。

1. 选择“数据”，然后选择“实体”。

1. 选择“流审批”实体的省略号 (…)，然后在 Microsoft Excel 中打开数据。

1. 在 Microsoft Excel 中，根据需要搜索、筛选并删除审批数据。

有关如何对使用 Common Data Service 的用户的 DSR 进行响应的其他指导，请参阅[针对 Common Data Service 客户数据执行 DSR](https://go.microsoft.com/fwlink/?linkid=872251)。

## <a name="delete-connections-created-by-a-user"></a>删除由用户创建的连接

连接与连接器结合使用，用于建立与其他 API 和 SaaS 系统的连接。  连接包括对创建连接的用户的引用，因此可以将其删除以删除对用户的任何引用。

PowerApps Maker PowerShell cmdlet

用户可以使用 [PowerApps Maker PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448) 中的 Remove-Connection 函数删除其所有连接：

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

PowerApps Admin PowerShell cmdlet

不可用。

## <a name="delete-the-users-permissions-to-shared-connections"></a>删除用户的共享连接权限

PowerApps Maker PowerShell cmdlet

用户可以使用 [PowerApps Maker PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448) 中的 Remove-ConnectionRoleAssignment 函数删除其所有有关共享连接的连接角色分配。

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

> [!NOTE]
> 不删除连接资源，就不能删除所有者角色分配。
>
>

PowerApps Admin PowerShell cmdlet

不可用。

## <a name="delete-custom-connectors-created-by-the-user"></a>删除用户创建的自定义连接器

自定义连接器补充了现有的开箱即用连接器并允许连接到其他 API、SaaS 和自定义开发的系统。 自定义连接器包含对创建它们的用户的引用，因此可以将其删除以删除对用户的任何引用。

PowerApps Maker PowerShell cmdlet

用户可以使用 [PowerApps Maker PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448) 中的 Remove-Connector 函数删除其所有自定义连接器：

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

PowerApps Admin PowerShell cmdlet

不可用。

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>删除用户的共享自定义连接器权限

PowerApps Maker PowerShell cmdlet

用户可以使用 [PowerApps Maker PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448) 中的 Remove-ConnectorRoleAssignment 函数删除其所有有关共享自定义连接器的连接器角色分配。

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

> [!NOTE]
> 不删除连接资源，就不能删除所有者角色分配。
>
>

PowerApps Admin PowerShell cmdlet

不可用。

## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>删除或重新分配由用户创建的所有环境

作为管理员，在处理用户创建的每个环境的用户的 DSR 删除请求时，需要作出两个决定：

1. 如果确定组织中没有其他人使用环境，可以选择删除环境
1. 如果确定环境仍然是必需的，则可以选择不删除环境，并将自己（或组织中的其他用户）添加为“环境管理员”。
    > [!IMPORTANT]
    > 删除环境将永久删除环境中的所有资源，包括所有应用、流、连接等，因此，请在删除之前检查环境中的内容。
    >
    >

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>从 Microsoft Flow 管理中心授予对用户环境的访问权限

管理员可以对来自 [Microsoft Flow 管理中心](https://admin.flow.microsoft.com/)的特定用户创建的环境授予“管理员”访问权限。 有关管理环境的详细信息，请导航到[使用 Microsoft Flow 中的环境](https://docs.microsoft.com/flow/environments-overview-admin)。

## <a name="delete-the-users-permissions-to-all-other-environments"></a>删除用户对所有其他环境的权限

可以在环境中向用户分配权限（如“环境管理员”、“环境创建者”等），这些权限作为“角色分配”存储在 Microsoft Flow 服务中。

随着 Common Data Service for Apps 的引入，如果在环境中创建一个数据库，这些“角色分配”将作为记录存储在 Common Data Service for Apps 数据库实例中。

有关在环境中删除用户权限的详细信息，请导航到[使用 Microsoft Flow 中的环境](https://docs.microsoft.com/flow/environments-overview-admin)。
