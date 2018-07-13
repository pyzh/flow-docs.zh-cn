---
title: 面向管理员的环境概述 | Microsoft Docs
description: 使用、创建和管理 Microsoft Flow 中的环境
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
ms.openlocfilehash: cf1a618b9e0ed76147eb4ede2aed42111c66b4a5
ms.sourcegitcommit: 4a8d11e1768cd0ca96a60b6f5548a68c0c8999e5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "31007969"
---
# <a name="using-environments-within-microsoft-flow"></a>使用 Microsoft Flow 中的环境

## <a name="benefits"></a>优势

环境具有如下优点：

* **数据区域性**：可以在不同的区域创建绑定到相应地理位置的环境。 在环境中创建流时，该流会路由到该地理位置的所有数据中心。 这也提供了一个性能优势。

    如果用户位于欧洲，请在欧洲区域创建并使用环境。 如果用户位于美国，请在美国创建并使用环境。 

    > [!IMPORTANT]
    > 如果删除环境，则也会删除该环境中的所有流。 这适用于在该环境中创建的任何项目，包括连接、网关、PowerApps 等。
* **数据丢失防护**：作为管理员，并不希望流先从内部位置（如 OneDrive for Business 或包含薪金信息的 SharePoint 列表）获取数据，再公开发布此类数据（如发布到 Twitter）。 借助数据丢失防护，可以控制哪些服务能够在 Microsoft Flow 部署中共享数据。

    例如，可以将 SharePoint 和 OneDrive for Business 服务添加到仅限业务数据策略。 在此环境中创建的任何流都可以使用 SharePoint 和 OneDrive for Business 服务。 不过，它们无法与未添加到仅限业务数据策略的其他服务共享数据。

  > [!NOTE]
  > 某些许可证（包括 P2 许可证）可以使用数据丢失防护。

* **所有资源的隔离边界**：任何流、网关、连接、自定义连接器等都驻留在特定环境中。 这些资源不存在于其他任何环境中。
* **Common Data Service**：若要创建将数据插入服务的流，可以采用下列方法：

  * 将数据插入 Excel 文件，然后将 Excel 文件存储在云存储帐户（例如 OneDrive）中。
  * 创建 SQL 数据库，再将数据存储到其中。
  * 使用通用数据服务存储数据。

    每个环境最多可以在 Common Data Service 中对流使用 1 个数据库。 Common Data Service 访问权限取决于已购买的许可证；免费许可证不随附 Common Data Service 访问权限。

## <a name="limitations"></a>限制

尽管环境具有许多优点，但也带来了新的限制。 由于环境是隔离边界，因此永远无法使用跨环境引用资源的资源。 例如，可能无法执行以下操作：先在一个环境中创建自定义连接器，再在另一个环境中创建使用此自定义连接器的流。

## <a name="use-the-default-environment"></a>使用默认环境

所有用户都可以使用默认环境，任何用户都能在默认环境中创建流。

> [!TIP]
> 如果是预览版用户，则所有现有流都位于默认环境中。 预览版用户是指在 Microsoft Flow 公开发布 (GA) 之前使用它的人。

## <a name="the-admin-center"></a>管理中心

管理员使用管理中心来创建和管理环境。 可通过以下两种方法打开管理中心：

### <a name="option-1-select-settings"></a>选项 1：选择“设置”

1. 登录 [flow.microsoft.com](https://flow.microsoft.com)。
1. 选择“设置”齿轮，再从列表中选择“管理中心”：

   ![设置和管理员门户](./media/environments-overview-admin/settings.png)
1. 此时将打开管理员中心。

### <a name="option-2-open-adminflowmicrosoftcom"></a>选项 2：打开 admin.flow.microsoft.com

转到 [admin.flow.microsoft.com](https://admin.flow.microsoft.com)，并使用工作帐户登录。

## <a name="create-an-environment"></a>创建环境

1. 在“[Microsoft Flow 管理员中心](https://admin.flow.microsoft.com)”，选择“环境”。 此时，将看到全部现有环境：![环境](./media/environments-overview-admin/environments-list.png)
2. 选择“新建环境”，再输入必填信息：


   |     属性     |                                                 说明                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | 环境名称 |              输入环境的名称，例如 `Human Resources` 或 `Europe flows`。              |
   |      区域      | 选择托管环境的位置。 为了获得最佳性能，请使用最靠近用户的区域。 |
   | 环境类型 |                  根据许可证选择环境类型：“生产”或“试用”。                   |

     ![环境设置](./media/environments-overview-admin/new-environment-dialog.png)
3. 单击“创建环境”。
4. 现在，可以根据需要单击“创建数据库”或“跳过”。
5. 如果选择“创建数据库”，将看到为数据库设置“货币”和“语言”的提示。 此外，还可以选择部署示例应用和数据。

   ![数据库配置设置](./media/environments-overview-admin/create-database-dialog2.png)


现在，可以将用户添加到环境中。

## <a name="manage-your-existing-environments"></a>管理现有环境

1. 在“[Microsoft Flow 管理员中心](https://admin.flow.microsoft.com)”，选择“环境”：

   ![环境菜单项](./media/environments-overview-admin/select-environments.png)
1. 选择一个环境，打开其属性。
1. 转到“详细信息”选项卡，查看环境的其他相关信息，包括环境的创建者、地理位置等：

   ![“详细信息”选项卡](./media/environments-overview-admin/open-environment.png)
1. 选择“安全性”。

    如果在前述步骤中未选择“创建数据库”，“环境角色”中有以下两个选项：“环境管理员”和“环境创建者”：

    ![管理员角色](./media/environments-overview-admin/environment-roles.png)

    创建者可以在环境中新建资源，如流、数据连接和网关。

   > [!NOTE]
   > 用户无需是创建者，也能在环境中编辑资源。 每个创建者都会向不是环境创建者的用户授予权限，以决定谁可以编辑他/她的资源。
   > 
   > 

    管理员可以创建数据丢失防护策略，并执行其他管理任务，如创建环境、向环境添加用户、分配管理员/创建者特权。

   1. 依次选择“环境创建者”角色和“用户”：![创建者角色](./media/environments-overview-admin/add-environment-maker.png)
   1. 输入要为创建者角色指定的名称、电子邮件地址或用户组。
   1. 选择“保存”。

1. 在“安全性”中，选择“用户角色”：

    ![用户角色](./media/environments-overview-admin/security-user-roles.png)

    此时将列出所有现有角色，包括编辑或删除角色的选项。

    选择“新建角色”来创建新角色。
1. 在“安全性”中，选择“权限集”：

    ![权限设置](./media/environments-overview-admin/security-permission-set.png)

    此时，将看到全部现有权限集，以及角色编辑或删除选项。

    选择“新建权限集”，以新建权限集。
1. 如果未选择“创建数据库”来存储数据，此数据库属于 Common Data Service。 单击“安全性”选项卡时，将会看到转到“Dynamics 365 实例管理中心”的提示，以便在其中应用基于角色的安全性。
![Dynamics 安全性设置](./media/environments-overview-admin/Security-Link-D365.png)

1. 从环境/实例中的用户列表选择用户。
  ![Dynamics 安全性设置](./media/environments-overview-admin/D365-Select-User.png)

1. 向用户分配角色。

   ![向用户分配角色](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> 分配到这些环境角色的用户或组不会自动获取对环境数据库（若有）的访问权限，此类权限必须由数据库所有者单独授予。 
>
>

### <a name="database-security"></a>数据库安全性
能否创建和修改数据库架构，以及能否连接到在环境中预配的数据库内存储的数据，取决于数据库的用户角色和权限集。 可以在“安全性”选项卡的“用户角色”和“权限集”部分中，管理环境数据库的用户角色和权限集。 

   ![向用户分配角色](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>常见问题

### <a name="can-i-move-a-flow-between-environments"></a>我能否在环境之间移动流？

能，可以将流从一个环境导出，再导入另一个环境中。

### <a name="which-license-includes-the-common-data-service"></a>哪种许可证包括通用数据服务？

只有 Microsoft PowerApps 计划 2 包括使用通用数据服务创建数据库的权限。 但是，所有付费计划（Microsoft Flow 计划 1 和 2、Microsoft PowerApps 计划 1 和 2）都有使用通用数据服务的权限。

请访问 [Microsoft Flow 定价](https://flow.microsoft.com/pricing/)页，选择适合自己的计划。

请参阅[计费常见问题解答](billing-questions.md)文档，了解与计费相关的常见问题解答。

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>能否在环境外使用通用数据服务？

否。 通用数据服务需要一个环境。 [阅读详细信息](common-data-model-intro.md)。

### <a name="what-regions-include-microsoft-flow"></a>哪些区域包括 Microsoft Flow？

Microsoft Flow 支持 Office 365 支持的大多数区域。如需了解更多详情，请参阅[区域概述](regions-overview.md)。

### <a name="whats-needed-to-create-my-own-custom-environment"></a>创建用户自己的自定义环境需要什么？

具有 Microsoft Flow Plan 2 许可证的所有用户都可以创建自己的环境。 虽然所有 Microsoft Flow 用户都可以使用由 Plan 2 管理员创建的环境，但无法创建自己的环境。
