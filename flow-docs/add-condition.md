---
title: "向流添加条件 | Microsoft Docs"
description: "指定仅在符合条件的情况下，某个流才执行一个或多个任务。"
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
ms.date: 10/17/2017
ms.author: stepsic
ms.openlocfilehash: 135b3509a9412f7674a1e9cb2ada86ebd2bb9f4f
ms.sourcegitcommit: 01325305b9d2cf964acac9feb6cca0af66db7440
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2017
---
# <a name="add-a-condition-to-a-flow"></a>向流添加条件

指定仅在符合条件的情况下，某个流才执行一个或多个任务。 例如，指定仅在推文包含的关键字被反复推送至少 10 次的情况下，用户才会收到电子邮件。

## <a name="prerequisites"></a>先决条件

* 通过模板[创建流](get-started-logic-template.md) - 此教程[以此模板](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/)为例

## <a name="add-a-condition"></a>添加条件

1. 在 [Microsoft Flow](https://flow.microsoft.com) 的顶部导航栏中选择“我的流”。

    如果尚未登录，则可能需要登录。

1. 在流的列表中，选择一个已创建的流。

    此教程采用一个含 Twitter 触发器和 SharePoint 操作的示例。

1. 选择“编辑流”。

1. 在上一个操作下，选择“新建步骤”。

1. 选择“添加条件”。

    ![“条件”按钮](./media/add-condition/add-condition.png)

1. 在“条件”卡上，选择左侧框中的空区域。

    此时会打开“动态内容”列表。

1. 选择“转推计数”参数将其添加到方框中。

1. 在“条件”卡中间的框中，选择“大于或等于”。

1. 在右侧的框中输入 10。

    ![包含参数的“对象名称”框](./media/add-condition/specify-condition.png)

1. 选择要在条件内使用的操作的标题（如“创建项目”）并将其拖动到“如果是”文本下方。

    释放光标时，操作移入该框内。

    ![拖动操作](./media/add-condition/drag-action.png)

1. 根据需要配置操作。

1. 保存流。

## <a name="edit-in-advanced-mode"></a>在高级模式下编辑

还可以选择“在高级模式中进行编辑”来编写更多高级条件。 可以使用高级模式下“工作流定义语言”中的任何表达式。 了解所有可用[表达式](https://msdn.microsoft.com/library/azure/mt643789.aspx)。

## <a name="next-steps"></a>后续步骤

了解如何在高级模式的条件中[使用表达式](use-expressions-in-conditions.md)。
