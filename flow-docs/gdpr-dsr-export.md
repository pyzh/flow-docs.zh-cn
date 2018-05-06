---
title: Microsoft Flow GDPR 数据主体导出请求| Microsoft Docs
description: 了解如何使用 Microsoft Flow 来响应 GPDR 数据主体导出请求。
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
ms.openlocfilehash: 1e1fe346ba6ffb264985da0115714246a621ef5a
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>响应 Microsoft Flow 的 GDPR 数据主体导出请求

为了在你使用一般数据保护条例 (GDPR) 的过程中与你一同协作，我们开发了帮助你进行准备工作的文档。 该文档不仅介绍了我们为 GDPR 所做的准备工作，还分享了有关在 Microsoft 中使用 Microsoft Flow 时如何支持 GDPR 符合性的步骤示例。

## <a name="manage-export-requests"></a>管理导出请求

数据可移植性权限允许数据主体请求一个电子格式（即“结构化、常用、计算机可读和交互格式”）的个人数据的副本，它可能会被传输到其他数据控制者。

Microsoft Flow 提供了以下查找或导出特定用户的个人数据的经验：

* Website 访问：登录到 [PowerApps 管理中心](https://admin.powerapps.com/)或 [Microsoft Flow 管理中心](https://admin.flow.microsoft.com/)。

* PowerShell 访问：[PowerApps Admin PowerShell cdmlets](https://go.microsoft.com/fwlink/?linkid=871804)

|客户数据|网站访问|PowerShell 访问|
|-----------------|------------------|-------------------|
|系统生成的日志|[Office 365 服务信任门户](https://servicetrust.microsoft.com/)|
|运行历史记录|Microsoft Flow Maker 门户||
|用户作业|| |
|流|Microsoft Flow Maker 门户||
|流权限| Microsoft Flow Maker 门户和 Microsoft Flow 管理中心||
|用户详细信息|| |
|连接|Microsoft Flow Maker 门户| |
|连接权限|Microsoft Flow Maker 门户| |
|自定义连接器|Microsoft Flow Maker 门户| |
|自定义连接器权限|Microsoft Flow Maker 门户| |
|网关|Microsoft Flow Maker 门户|本地网关 PowerShell cmdlet|
|网关权限|Microsoft Flow Maker 门户|

## <a name="export-a-flow"></a>导出流

向自己授予访问流权限的最终用户或管理员可以通过执行以下步骤来导出流：

1. 登录到 [Microsoft Flow](https://flow.microsoft.com/)。

1. 选择“我的流”链接，然后选择要导出的流。

1. 选择“...更多”，然后选择“导出”。

    ![导出流](./media/gdpr-dsr-export/export-flow.png)

1. 选择“包(.zip)”。

现在，你的流将以压缩包的形式提供给你。 有关详细信息，请参阅有关[如何导出和导入流](https://flow.microsoft.com/blog/import-export-bap-packages/)的博客文章。

## <a name="export-run-history"></a>导出运行历史记录

运行历史记录包括为流执行的所有操作的列表。 此数据包括流的状态、开始时间、持续时间以及触发器和操作的输入/输出数据。

通过 Microsoft Flow 管理中心被授予流访问权限的最终用户或管理员可执行以下步骤来导出此数据：

1. 登录到 [Microsoft Flow](https://flow.microsoft.com/)。
1. 选择“我的流”链接，然后选择想要导出运行历史记录的流。
1. 在“运行历史记录”窗格中，选择“查看所有”。

    ![运行历史记录](./media/gdpr-dsr-export/run-history.png)

1. 选择“下载 CSV”。

    ![下载 CSV](./media/gdpr-dsr-export/download-csv.png)

运行历史记录被下载为 .csv 文件，以便你在 Microsoft Excel 或文本编辑器中打开，并进一步分析结果。

## <a name="export-a-users-activity-feed"></a>导出用户的活动源

在 [Microsoft Flow](https://flow.microsoft.com/) 中，活动源显示用户的活动、失败和通知的历史记录。 任何用户都可以通过执行以下步骤来查看他们的活动源：

1. 登录到 [Microsoft Flow](http://flow.microsoft.com/)，选择右上角旁的钟形图标，然后选择“显示所有活动”。

    ![显示活动源](./media/gdpr-dsr-export/show-activity-feed.png)

1. 在“活动”屏幕中，复制结果，然后将其粘贴到文档编辑器（例如，Microsoft Word）中。

    ![显示活动源](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>导出用户的连接

连接允许流连接到 API、SaaS 应用程序和其他第三方系统。 请按照以下步骤来查看你的连接：

1. 登录到 [Microsoft Flow](http://flow.microsoft.com/)，选择右上角旁的齿轮图标，然后选择“连接”。

    ![显示连接](./media/gdpr-dsr-export/show-connections.png)
1. 复制结果，然后将其粘贴到文档编辑器（例如，Microsoft Word）中。

## <a name="export-a-list-of-a-users-connection-permissions"></a>导出用户的连接权限的列表

用户可以导出他们有权访问的所有连接的连接角色分配，方法是通过调用 [PowerApps PowerShell cdmlets](https://go.microsoft.com/fwlink/?linkid=871804) 中的 Get-ConnectionRoleAssignment 函数。
![导出连接权限](./media/gdpr-dsr-export/export-connection-permissions.png)

## <a name="export-a-users-custom-connectors"></a>导出用户的自定义连接器

自定义连接器补充了现有开箱即用连接器并允许连接到其他 API、SaaS 和自定义开发的系统。 可以转移自定义连接器的所有权或将其删除。

请按照以下步骤来导出客户连接器的列表：

1. 导航到 [Microsoft Flow](https://flow.microsoft.com)。
1. 选择设置“齿轮”图标。
1. 选择“自定义连接器”。
1. 复制自定义连接器列表并将其粘贴到文本编辑器（例如，Microsoft Word）中。

    ![导出自定义连接器](./media/gdpr-dsr-export/export-custom-connectors.png)

除了 Microsoft Flow 中所提供的经验以外，还可以使用 [PowerApps PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804) 中的 Get-Connector 函数来导出所有自定义连接器。

![导出自定义连接器 powershell](./media/gdpr-dsr-export/export-custom-connectors-powershell.png)

## <a name="export-a-users-custom-connector-permissions"></a>导出用户的自定义连接器权限

用户可以导出他们所创建的所有自定义连接器权限，方法是使用 [PowerApps PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804) 中的 Get-ConnectorRoleAssignment 函数。

![导出自定义连接器权限 powershell](./media/gdpr-dsr-export/export-connector-permissions.png)

## <a name="export-approval-history"></a>导出审批历史记录

Microsoft Flow 审批历史记录会捕获已为用户接收或发送的审批的历史记录。 任何用户都可以通过执行以下操作来查看他们的审批历史记录：

1. 登录到 [Microsoft Flow](http://flow.microsoft.com/)，选择“审批”，然后选择“历史记录”。

    ![查看审批历史记录](./media/gdpr-dsr-export/view-approval-history.png)

1. 出现一个列表，显示用户接收的审批。 用户可以显示他们发送的审批，方法是选择“接收”旁的向下箭头，然后选择“发送”。

    ![查看接收的审批](./media/gdpr-dsr-export/view-received-approvals.png)
