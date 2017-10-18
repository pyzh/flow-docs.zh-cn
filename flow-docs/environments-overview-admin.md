---
title: "面向管理员的环境概述 | Microsoft Docs"
description: "使用、创建和管理 Microsoft Flow 中的环境"
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: f1c50e5d16d5b9fbbd3e6db3128947b0554e9a85
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="using-environments-within-microsoft-flow"></a>使用 Microsoft Flow 中的环境
## <a name="benefits"></a>优势
环境是 Microsoft Flow 中的新功能，包括以下优势： 

* **数据本地化**：可以在不同区域创建环境并将其绑定到该地理位置。 在环境中创建流时，该流会路由到该地理位置的所有数据中心。 这也提供了一个性能优势。 
  
    如果用户位于欧洲，则在欧洲区域创建并使用环境。 如果用户位于美国，则在美国创建并使用环境。 
  
    如果删除环境，则也会删除该环境中的所有流。 这适用于在该环境中创建的任何项目，包括连接、网关、PowerApps 等。
* **数据丢失防护**：作为管理员，您不希望流从内部位置（如 OneDrive for Business）获取数据，然后公开发布该数据（如发布到 Twitter）。 使用数据丢失防护，控制哪些服务可以在仅限业务数据策略中使用。 
  
    例如，可以将 *SharePoint* 和 *OneDrive for Business* 服务添加到仅限业务数据策略。 在此环境中创建的任何流都可以使用这些 *SharePoint* 和 *OneDrive for Business* 服务。 仅用户添加的服务可用。 
  
  > [!NOTE]
  > 某些许可证（包括 P2 许可证）可以使用数据丢失防护。 
  > 
  > 
* **所有资源的隔离边界**：该特定环境中的任何流、网关、连接、自定义连接器等。 这些资源不存在于任何其他环境中。 
* **通用数据服务**：用户需要创建一个用于在某处插入数据的流。 选项包括：
  
  * 将数据插入 Excel 文件，然后将 Excel 文件存储在云存储帐户（例如 OneDrive）中。
  * 创建自己的 SQL 数据库，将数据存储在其中。
  * 使用通用数据服务存储数据。
    
    每个环境都可以在通用数据服务中为流设置 0 或 1 个数据库存储。 通用数据服务访问权限取决于所购买的许可证；免费许可证不提供此类权限。

## <a name="limitations"></a>限制
虽然环境提供了许多优势，但也带来了新的限制。 环境是隔离边界的事实意味着用户永远不会有跨环境引用其他资源的资源。 例如，无法在一个环境中创建自定义连接器并在另一个环境中创建使用该自定义连接器和网关的流。

因此，务必在必要时才创建环境。 创建过多环境将使组织内的用户很难共享资源。

## <a name="use-the-default-environment"></a>使用默认环境
**默认**环境适用于每个用户，并由所有用户共享。 每位用户都可以在此环境中创建流。

> [!TIP]
> 如果是预览版用户，则所有现有流都位于默认环境中。 预览版用户是指在 Microsoft Flow 公开发布 (GA) 之前使用它的人。 
> 
> 

## <a name="use-the-administrator-center"></a>使用管理员中心
管理员使用管理员中心来创建环境，将用户添加到这些环境中，以及其他类似的任务中。 打开管理员中心的方法有两种：

#### <a name="option-1-select-settings"></a>选项 1：选择“设置”
1. 登录 [flow.microsoft.com](https://flow.microsoft.com)。
2. 选择“设置”齿轮，然后从列表中选择“管理中心”：  
   ![设置和管理员门户](./media/environments-overview-admin/settings.png)
3. 此时将打开管理员中心。

#### <a name="option-2-open-adminflowmicrosoftcom"></a>选项 2：打开 admin.flow.microsoft.com
转到 [admin.flow.microsoft.com](https://admin.flow.microsoft.com)，并使用工作帐户登录。 此时将打开管理员中心。

## <a name="create-an-environment"></a>创建环境
1. 在“[Microsoft Flow 管理员中心](https://admin.flow.microsoft.com)”，选择“环境”。 此时会显示任何现有的环境：  
   ![](./media/environments-overview-admin/environments-list.png)
2. 选择“新建环境”。 输入以下信息：
   
   | 属性 | 说明 |
   | --- | --- |
   | 环境名称 |输入环境的名称，例如 `Human Resources` 或 `Europe flows`。 |
   | 区域 |选择托管环境的位置。 为了获得最佳性能，请使用最靠近用户的区域。 例如，如果流用户位于伦敦，则可选择“欧洲”作为区域。 如果流用户位于纽约，则可选择“美国”作为区域。 |
3. 选择“创建环境”。 此时会列出新环境。 

接下来，将用户添加到环境。

## <a name="manage-your-existing-environments"></a>管理现有环境
1. 在“[Microsoft Flow 管理员中心](https://admin.flow.microsoft.com)”，选择“环境”：  
   ![](./media/environments-overview-admin/select-environments.png)  
2. 选择一个环境，打开其属性。 
3. “详细信息”中会显示有关环境的其他信息，包括环境的创建者、地理位置以及其他属性：  
   ![](./media/environments-overview-admin/open-environment.png)
4. 选择“安全性”。 在“环境角色”中，有两个选项：“管理员”和“创建者”：  
   
    ![](./media/environments-overview-admin/environment-roles.png)
   
    “创建者”可以在环境中创建新的资源，例如流、数据连接、网关。 
   
   > [!NOTE]
   > 用户不需要成为**创建者**以在环境中编辑资源，只需创建全新资源即可。 每个资源创建者可以确定哪些用户可编辑该资源，并且可以向不是环境创建者的用户授予编辑权限。
   > 
   > 
   
    “管理员”可以创建数据丢失防护策略，也可以完成管理任务，例如创建环境、向环境添加用户，以及分配管理员/创建者权限。  
   
   1. 选择“环境创建者”角色，然后选择“用户”：  
      ![](./media/environments-overview-admin/add-environment-maker.png)
   2. 输入要提供给“创建者”角色的名称、电子邮件地址或用户组。 你一开始键入，智能感知就会开始列出与你的文本匹配的用户/组。 
   3. 选择“保存”，完成添加用户的操作。 
5. 在“安全性”中，选择“用户角色”：  
    ![](./media/environments-overview-admin/security-user-roles.png)
   
    此时将列出所有现有角色，包括编辑或删除角色的选项。 
   
    选择“新建角色”来创建新角色。 
6. 在“安全性”中，选择“权限集”：  
    ![](./media/environments-overview-admin/security-permission-set.png)
   
    此时将列出所有现有权限集，包括编辑或删除角色的选项。 
   
    选择“新建权限集”来创建新权限集。 
7. 在“数据库”中，用户可以选择创建数据库来存储数据。 此数据库是 Common Data Service 的一部分。

## <a name="commonly-asked-questions"></a>常见问题
##### <a name="can-i-migrate-a-microsoft-flow-in-my-us-environment-to-a-europe-environment"></a>能否将美国环境中的 Microsoft Flow 迁移到欧洲环境？
否，不能在环境之间移动流。 在另一个环境中重新创建流。

##### <a name="which-license-includes-the-common-data-service"></a>哪种许可证包括通用数据服务？
只有 Microsoft PowerApps 计划 2 包括使用通用数据服务创建数据库的权限。 但是，所有付费计划（Microsoft Flow 计划 1 和 2、Microsoft PowerApps 计划 1 和 2）都有使用通用数据服务的权限。

可以根据 [Flow 定价](https://flow.microsoft.com/pricing/)选择合适的计划。  

也可参阅[计费问题](billing-questions.md)，了解部分常见问题。 

##### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>能否在环境外使用通用数据服务？
否。 通用数据服务需要一个环境。 [阅读详细信息](common-data-model-intro.md)。

##### <a name="what-regions-include-microsoft-flow"></a>哪些区域包括 Microsoft Flow？
Microsoft Flow 支持 Office 365 支持的大多数区域，请参阅[区域概述](regions-overview.md)了解更多详细信息。

##### <a name="what-is-needed-to-create-my-own-custom-environment"></a>创建用户自己的自定义环境需要什么？
除了默认环境之外，具有 Microsoft Flow 计划 2 许可证的所有用户还可以创建自己的环境。 所有 Microsoft Flow 用户（包括 Office 365 和免费版）都可以使用由计划 2 管理员创建的环境，但是无法创建其自己的环境。 

