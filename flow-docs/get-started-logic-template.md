---
title: "通过模板创建流 | Microsoft Docs"
description: "从多个内置模板中的任一个创建流"
services: 
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
ms.author: anneta
ms.openlocfilehash: 876723b62274f3a306c0a8472095b131e223408b
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>在 Microsoft Flow 中通过模板创建流
通过多个内置模板中的任一个创建一个具有特定用途的流，例如，该流在用户的经理在 Office 365 中向用户发送电子邮件时，可以向用户发送 Slack 消息。

**注意：** 如果脑中已经有了某个过程，但找不到相应的模板，则可[从头开始创建流](get-started-logic-flow.md)。

**先决条件**

* 在 [flow.microsoft.com](https://flow.microsoft.com) 上有一个帐户
* Slack 帐户
* Office 365 凭据

## <a name="choose-a-template"></a>选择模板
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. 在 [flow.microsoft.com](https://flow.microsoft.com) 的顶部导航栏中选择“模板”。
2. 在搜索栏中，键入 **Slack**，然后选择搜索图标。
3. 用户只会看到与 Slack 相关的模板，因此现在可以选择“当经理向我发送电子邮件时在 Slack 上发送消息”。
   
    ![左侧导航栏中的新选项](./media/get-started-logic-template/select-template.png)
4. 确认此模板将执行用户要执行的操作，然后选择“使用此模板”。
5. 如果尚未登录 Office 或 Slack，请选择“登录”，然后按提示操作。
   
    ![模板所需连接的列表](./media/get-started-logic-template/confirm-connections.png)
6. 确认连接后，选择“继续”。
   
    此时会出现用户的流，显示每个操作都带有一个橙色标题栏。
   
    ![模板中的默认事件和操作](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>自定义流
1. 选择事件的标题栏将其展开，然后对其进行自定义（例如，可以指定一个筛选器，筛选出自己感兴趣的电子邮件）。
2. 需要从用户获得输入的操作会自动展开。
   
    例如，“发布消息”操作会展开，因为你需要输入一个通道，例如 @username。 也可以自定义消息内容。 默认情况下，消息将只包含主题，但也可包含其他信息。
   
    ![为 Slack 指定通道](./media/get-started-logic-template/specify-keyword.png)
3. 在屏幕顶部附近，为流指定名称，然后选择“创建流”。
4. 最后，如果对流满意，请选择“完成”。
   
    ![“完成”按钮](./media/get-started-logic-template/done.png)

现在，当用户的经理向用户发送电子邮件时，用户会收到 Slack 消息，其中包含用户指定的信息。

## <a name="next-steps"></a>后续步骤
* [观看运行中的流](see-a-flow-run.md)
* [发布自己的模板](publish-a-template.md)
* [使用通用数据服务的模板](common-data-model-intro.md)
* [开始使用团队流](create-team-flows.md)并邀请其他人与你协作来设计流。

