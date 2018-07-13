---
title: 创建并行现代审批工作流 | Microsoft Docs
description: 创建并行现代审批工作流
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2018
ms.author: deonhe
ms.openlocfilehash: 43b748332a649e5f8d8db5fbe11f53522ce8bb79
ms.sourcegitcommit: 4a8d11e1768cd0ca96a60b6f5548a68c0c8999e5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38949737"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>使用 Microsoft Flow 创建并行审批工作流

在并行审批工作流中，需要多名人员批准发票、采购订单、休假请求等项目。每个人员的审批与所有其他审批者无关。

在本演练中，我们将使用 Microsoft Flow 来创建自动执行并行审批工作流的流。 此流自动执行员工休假请求过程，该过程需要获得该员工经常支持的所有人员（或组）的批准。 员工使用 [SharePoint 列表](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7)来请求休假。 需要该员工的直属经理、销售团队和人力资源团队批准休假。 每个休假请求都会路由给每个审批者以做出决策。 该流发送状态发生更改的电子邮件，然后根据这些决策更新 SharePoint。

## <a name="prerequisites"></a>先决条件

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

所创建的 SharePoint Online 列表必须包含以下列：

   ![SharePoint 列表列](./media/parallel-modern-approvals/sharepoint-columns.png)

请记下 SharePoint Online 列表的名称和 URL。 稍后我们将使用这些项来配置“SharePoint - 当创建项时”触发器。

## <a name="create-your-flow-from-the-blank-template"></a>从空白模板创建流

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>添加触发器

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Sharepoint 信息](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>获取创建休假请求的人员的管理器。

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>命名并保存流

1. 为流提供一个名称，然后选择“保存”图标来保存目前为止已进行的工作。

   ![保存流](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> 定期选择“保存”图标将所作更改保存到流中。
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>添加直属经理审批操作

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> 此操作将休假请求发送至“分配到”框中的电子邮件地址，进而插入“联系经理(v2)”列表中的“电子邮件”令牌。
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>插入销售团队并行分支审批操作

1. 选择位于“联系经理(v2)”和“开始审批”卡之间的向下箭头。
2. 选择选中向下箭头后出现的加号。
3. 选择“添加并行分支”。
4. 选择“添加操作”。

    ![获取管理器配置](./media/parallel-modern-approvals/add-parallel-branch.png)
5. 搜索、选择然后配置“启动审批”操作，将休假请求发送到销售团队。 如果不确定如何添加“启动审批”操作，请参阅[用于添加直属经理审批操作的步骤](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager)。

> [!IMPORTANT]
> 使用“开始审批 2”操作的“分配到”框中的销售团队电子邮件地址。
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>插入人力资源团队并行分支审批操作

1. 重复[插入销售团队并行分支](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team)步骤以添加并配置“启动审批”操作，来向人力资源发送休假请求。

> [!IMPORTANT]
> 使用“开始审批 3”操作的“分配到”框中的人力资源团队电子邮件地址。
> 
> 

如果已按照上述步骤执行操作，流应类似于以下示例：

   ![具有并行分支的流](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>添加并行分支后的选项

将操作添加到并行分支后，可以通过两个选项将更多步骤添加到流：

1. 使用“插入新步骤”小按钮（当选择分支或分支正下方的区域上的任意空白区域时出现的圆形加号按钮）。 此按钮将步骤添加到该特定分支。 在此特定分支完成后，将运行使用此按钮添加的步骤。
1. 使用位于整个工作流底部的“新建步骤”大按钮。 在所有分支完成后，将运行使用此按钮添加的步骤。

在以下部分中，我们将使用“插入新步骤”小按钮在每个分支上执行这些步骤：

* 添加一个条件，检查休假请求是被批准还是被拒绝。
* 发送电子邮件，告知员工相关决策。
* 使用该审批决策更新 SharePoint 中的休假请求。

然后，我们使用“新建步骤”大按钮发送电子邮件，其中概述了针对休假请求所做的所有决策。

继续以下操作：

## <a name="add-a-condition-to-each-branch"></a>向每个分支添加条件

1. 在“启动审批”分支上选择任意空白区域。
2. 选择“插入新步骤”小按钮（选择上一步骤中的空白区域后出现的圆形加号按钮）。
3. 从显示的菜单中选择“添加条件”。
4. 选择“条件”卡上的第一个框，然后从动态内容列表的“启动审批”类别中选择“响应”令牌。

    ![具有并行分支条件的流](./media/parallel-modern-approvals/configure-approval-condition.png)
5. 确认列表（“条件”卡中间）已设置为“等于”。
6. 在最后一个框中输入“批准”（此文本区分大小写）。
7. “条件”卡现在应类似于以下示例：

    ![具有并行分支条件的流](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > 此条件从“启动审批”操作检查传递给员工经理的响应。
   > 
   > 
8. 在“启动审批 2”（对销售团队的审批请求）和“启动审批 3”（对人力资源的审批请求）分支上重复上述步骤。

## <a name="add-email-actions-to-each-branch"></a>向每个分支添加电子邮件操作

在“条件”分支的“如果是”侧执行下列步骤。

   注意：请求得到批准时，流将使用这些步骤发送电子邮件：

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![配置预先批准的电子邮件模板](includes/media/parallel-modern-approvals/yes-email-config.png)

若要在请求被拒时发送电子邮件，请使用“条件”分支的“如果否”侧，然后重复上述步骤以添加拒绝电子邮件模板。

在“启动审批 2”（对销售团队的审批请求）和“启动审批 3”（对人力资源的审批请求）分支上重复上述步骤。

## <a name="update-the-vacation-request-with-the-decision"></a>根据决策更新休假请求

做出决策后，执行以下步骤更新 SharePoint。

   注意：请确保同时在分支的“如果是”和“如果否”两侧执行这些步骤。

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![更新项目配置](./media/parallel-modern-approvals/configure-update-item.png)

在“启动审批 2”和“启动审批 3”分支上重复上述步骤。

## <a name="complete-the-flow"></a>完成流

1. 选择“新建步骤” > “添加操作”

    ![更新项目配置](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. 使用先前提供的步骤发送汇总每个审批结果的电子邮件。 将此电子邮件发送给请求休假的员工。 卡可能类似于以下示例：

   ![更新项目配置](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>了解有关现代审批的详细信息

[现代审批简介](modern-approvals.md)

