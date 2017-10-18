---
title: "使用 Microsoft Flow 审批请求 | Microsoft Docs"
description: "了解如何使用 Microsoft Flow 来管理审批工作流。"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: o-pgEBW3fOI
courseduration: 14m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 049b713ed653ab5555e5f48f63e46cce7f3207ee
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="approval-requests"></a>审批请求
除了帮助**接收通知**、**复制文件**和**收集数据**之外，Microsoft Flow 还可以帮助**简化审批过程**。

## <a name="vacation-scenario"></a>休假方案
假设你是团队的**管理人员**，你要求员工在 **SharePoint 列表**中创建**休假请求**。 现在你想要围绕这些列表项构建**审批过程**，以便新的休假请求将被**快速处理**，并且请求者将被**自动通知**。  

## <a name="sharepoint-and-microsoft-flow"></a>SharePoint 和 Microsoft Flow
**SharePoint** 已**内置**了 Microsoft Flow。  从你的 **SharePoint 列表**中，单击“流”下拉列表，然后单击“创建流”。

![创建流](./media/learning-approvals/new-flow.png)   

在**右侧的菜单**中查找**模板**，如下所示。

![审批模板](./media/learning-approvals/approval-template.png)

## <a name="using-the-template"></a>使用模板
模板中的 **SharePoint** 触发器**预先填充**了你的列表信息。  你需要执行的全部操作就是为**审批者**添加**电子邮件地址**。  请注意，这**不会更改原始的 SharePoint 项目**。  为此，我们需要添加“SharePoint - 更新项目”操作。

![更新项目](./media/learning-approvals/update-item.png)

“发送电子邮件的范围”的“否则”分支是怎样的？  默认情况下，它不会执行任何操作。  你可能需要添加一个操作，以便向请求的作者发送消息，告诉他们其请求已被拒绝。 

![否则](./media/learning-approvals/if-no.png)

## <a name="next-lesson"></a>下一课
现在，我们将回顾我们在本部分中了解的内容。

