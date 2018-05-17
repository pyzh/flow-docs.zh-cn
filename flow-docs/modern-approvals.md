---
title: 轻松地自动执行审批工作流。 | Microsoft Docs
description: 自动执行与 SharePoint、Dynamics CRM、Salesforce、OneDrive for Business、Zendesk 或 WordPress 集成的审批工作流。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
ms.openlocfilehash: bd89bca994a77072815a73ba1cbc7ba1db6955d3
ms.sourcegitcommit: e52f04b5953240d71d726c0e3373740cc59292dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>通过 Microsoft Flow 创建和测试审批工作流

使用 Microsoft Flow 可以跨多个服务管理文档或流程的审批，这些服务包括：SharePoint、Dynamics CRM、Salesforce、OneDrive for Business、Zendesk 或 WordPress。

若要创建审批工作流，请向任意流添加“审批 - 启动审批”操作。 添加此操作后，即可通过流来管理文档或流程的审批。 例如，可以创建文档审批流来审批发票、工作订单或销售报价单。 还可以创建流程审批流来审批休假请求、加班或旅行计划。

审批者可以回复来自其电子邮件收件箱、Microsoft Flow 网站上的[审批中心](https://flow.microsoft.com/manage/approvals/received/)或 Microsoft Flow 应用的请求。

## <a name="create-an-approval-flow"></a>创建审批流
下面是我们将创建和测试的流的概览：

   ![流概览](./media/modern-approvals/create-flow-overview.png)

流执行以下步骤：

1. 当某人在 SharePoint Online 列表中创建休假请求时启动。
2. 将休假请求添加到审批中心，并通过电子邮件将其发送给审批者。
3. 将一封电子邮件连同审批者的决定发送给请求休假的人员。
4. 使用审批者的决策注释更新 SharePoint Online 列表。

## <a name="prerequisites"></a>先决条件
若要完成本演练，你必须有执行以下操作所需的访问权限：

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

在 SharePoint Online 列表中创建以下列：

   ![SharePoint Online 列表列](./media/modern-approvals/sharepoint-list-fields.png)

请记下 SharePoint Online 列表的名称和 URL。 稍后在配置“SharePoint - 当创建项时”触发器时，将需使用这些项。

## <a name="create-your-flow-from-the-blank-template"></a>从空白模板创建流
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>添加触发器

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

“站点地址”和“列表名称”是你在本演练中的前面部分记下的项。

![Sharepoint 信息](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>添加“配置文件”操作

1. 选择“新建步骤”，然后选择“添加操作”。
   
    ![新建步骤](./media/modern-approvals/select-sharepoint-add-action.png)
2. 将“配置文件”输入到“选择操作”搜索框。
   
    ![搜索配置文件](./media/modern-approvals/search-for-profile.png)
3. 查找并选择“Office 365 用户 - 获取我的配置文件”操作。
   
    ![选择 Office 用户](./media/modern-approvals/select-my-profile.png)
4. 为你的流提供一个名称，然后选择“创建流”保存目前为止已进行的工作。
   
    ![保存流](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>添加“审批”操作

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> 此操作会将审批请求发送至“分配到”框中的电子邮件地址。
>
>

## <a name="add-a-condition"></a>添加条件

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>添加电子邮件操作以用于审批

如果休假请求已经被批准，请按照下列步骤发送一封电子邮件：

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![配置已批准的电子邮件模板](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>添加用于已批准请求的更新操作

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> “站点地址”、“列表名称”、“ID”和“标题”是必填项。
>
>

![更新项目配置](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>添加电子邮件操作以用于拒绝

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![已拒绝的请求的配置](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>添加用于已拒绝请求的更新操作

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > “站点地址”、“列表名称”、“ID”和“标题”是必填项。
   >
   >

![更新项目卡](./media/modern-approvals/configure-update-item-no.png)

1. 选择“更新流”以保存已完成的工作。
   
    ![选择更新操作](./media/modern-approvals/update.png)

如果已按照上述步骤执行操作，流应类似于此屏幕截图：

![流概览](./media/modern-approvals/completed-flow.png)

既然已创建了流，现在就要对其进行测试了！

## <a name="request-an-approval"></a>请求批准

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

创建并测试流以后，请务必让他人知道如何使用该流。

## <a name="learn-more"></a>了解详情

* 查看和管理[待审批请求](approve-reject-requests.md)
* 创建[顺序审批流](sequential-modern-approvals.md)。
* 创建[并行审批流](parallel-modern-approvals.md)。
* 安装适用于 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows) 的 Microsoft Flow 移动应用。
