---
title: "向流添加条件 | Microsoft Docs"
description: "指定仅在符合特定条件的情况下，某个流才执行一个或多个任务。"
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: 1291b32f001be211acddbf1c83f3b1bdf03f2ac3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="add-a-condition-to-a-flow"></a>向流添加条件
指定仅在符合特定条件的情况下，某个流才执行一个或多个任务。 例如，指定仅在推文包含的关键字被反复推送至少 10 次的情况下，用户才会收到电子邮件。

**先决条件**

* 通过模板[创建流](get-started-logic-template.md) - 此教程将[以此模板](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/)为例

## <a name="add-a-condition"></a>添加条件
1. 在 [flow.microsoft.com](https://flow.microsoft.com) 的顶部导航栏中选择“我的流”。
2. 在流列表中，选择已创建的流。 此教程采用一个含 Twitter 触发器和 SharePoint 操作的示例。
3. 在上一个操作下，选择“新建步骤”按钮。
4. 选择“添加条件”。
   
    ![“条件”按钮](./media/add-a-condition/add-condition.png)
5. 在“对象名称”中选择空白区域，然后选择“添加动态内容”以打开动态内容菜单。
6. 选择“转推计数”参数将其添加到方框中。
7. 在“关系”框中，选择“大于或等于”。
8. 在“值”框中，键入“10”。
   
    ![包含参数的“对象名称”框](./media/add-a-condition/specify-condition.png)
9. 单击要在条件内执行的操作的标题（如“创建项目”）并将其拖动到“如果是”文本下方。 释放光标时，操作应移入该方框内。
   
    ![拖动操作](./media/add-a-condition/drag-action.png)
10. 保存流。

## <a name="edit-in-advanced-mode"></a>在高级模式下编辑
用户还可以选择“在高级模式下编辑”链接来编写更多高级条件。 用户可以使用此处“工作流定义语言”的任何表达式。 [详细了解](https://msdn.microsoft.com/library/azure/mt643789.aspx)哪些功能可用。

