---
title: "通过创建流来自动执行任务 | Microsoft Docs"
description: "创建流即可在发生相关事件时自动执行一个或多个操作，例如发送邮件、将某一行添加到 SharePoint 列表。"
services: 
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: deonhe
ms.openlocfilehash: fd6ed3973ed09442108bf780f76b750deea20eeb
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-in-microsoft-flow"></a>在 Microsoft Flow 中创建流
<iframe width="560" height="315" src="https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

创建一个流，该流在受到事件触发后自动执行一个或多个任务。 例如，可以创建一个流，在别人发送的推文包含指定的关键字时通过电子邮件通知你。 在此示例中，发送推文是事件，发送邮件是操作。

## <a name="prerequisites"></a>先决条件
* 在 [flow.microsoft.com](https://flow.microsoft.com) 上有一个帐户
* Twitter 帐户
* Office 365 凭据

## <a name="specify-an-event-to-start-the-flow"></a>指定一个可启动流的事件
首先需选择通过什么事件或触发器来启动流。

1. 在 [flow.microsoft.com](https://flow.microsoft.com) 的顶部导航栏中选择“我的流”，然后选择“从空白模板开始创建”。
   
    ![左侧导航栏中的流选项](./media/get-started-logic-flow/create-logic-flow.png)
2. 在“搜索所有连接器和触发器”框中，键入或粘贴“Twitter”，然后选择“Twitter - 当新推文发布时”。
   
    ![Twitter 事件](./media/get-started-logic-flow/twitter-search.png)
3. 如果尚未将 Twitter 帐户连接到 Microsoft Flow，请选择“登录到 Twitter”，然后提供凭据。
   
    ![Twitter 登录](./media/get-started-logic-flow/twitter-signin.png)
4. 在“搜索文本”框中，键入想要查找的关键字。
   
    ![Twitter 关键字](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>指定操作
1. 选择“新建步骤”，然后选择“添加操作”。
   
    ![添加操作](./media/get-started-logic-flow/add-action-icon.png)
2. 在显示“搜索所有连接器和操作”的框中，键入或粘贴“发送电子邮件”，然后选择“Office 365 Outlook - 发送电子邮件”。
   
    ![操作列表](./media/get-started-logic-flow/send-email.png)
3. 如果系统提示，请选择登录按钮，然后提供凭据。
4. 在出现的窗体的“收件人”框中，键入或粘贴电子邮件地址，然后从出现的联系人列表中选择名称。
   
    ![空白电子邮件](./media/get-started-logic-flow/blank-email.png)
5. 在“主题”框中，键入或粘贴“新推文来源:”，然后键入一个空格。
   
    ![带占位符的主题行](./media/get-started-logic-flow/message-token.png)
6. 在令牌列表中，选择“推送者” 令牌，为其添加一个占位符。
   
    ![添加参数](./media/get-started-logic-flow/add-parameter.png)
7. 单击或点击“正文”框，然后单击或点击“推文文本”令牌，为其添加一个占位符。
8. （可选）在电子邮件的正文中添加更多令牌和/或其他内容。
9. 在屏幕顶部附近，为流命名，然后选择“创建流”。
   
    ![选择“创建流”按钮](./media/get-started-logic-flow/create-button.png)
10. 选择“完成”更新流列表。
    
     ![选择“完成”按钮](./media/get-started-logic-flow/done-button.png)
11. 发送推文，其中包含所指定的关键字。
    
     在一分钟之内，电子邮件会通知用户有新推文。

## <a name="manage-a-flow"></a>管理流
1. 在 [flow.microsoft.com](https://flow.microsoft.com) 的顶部导航栏中选择“我的流”。
2. 在流列表中，执行下列任一操作：
   
   * 若要暂停流，请将其开关设置为“关闭”。
     
       ![暂停流](./media/get-started-logic-flow/pause-flow.png)
   * 若要恢复流，请将其开关设置为“打开”。 
     
       ![恢复流](./media/get-started-logic-flow/resume-flow.png)
   * 若要编辑流，请选择与要编辑的流相对应的铅笔图标。
     
       ![选择流](./media/get-started-logic-flow/select-flow.png)
   * 若要删除流，请先选择“...”图标和“删除”，然后在显示的消息框中选择“删除”。
     
       ![“删除”图标](./media/get-started-logic-flow/delete-icon.png)
   * 若要查看流的运行历史记录，请从“我的流”页中选择该流，然后在已打开页面的“运行历史记录”部分查看历史记录。
     
       ![运行历史记录](./media/get-started-logic-flow/run-history.png)
     
     从运行列表中选择流运行，查看每一步的输入和输出。

**注意**：帐户中最多可以有 50 个流。 如果已经有 50 个，则需先删除一个才能创建另一个。

## <a name="next-steps"></a>后续步骤
* 向流[添加步骤](multi-step-logic-flow.md)，例如不同的通知方式。
* [按计划运行任务](run-tasks-on-a-schedule.md)：用户需要将操作执行时间设置为每天、特定日期或数分钟后。
* [向应用添加流](https://powerapps.microsoft.com/tutorials/using-logic-flows/)：目的是允许应用在云中启动逻辑。
* [开始使用团队流](create-team-flows.md)并邀请其他人与你协作来设计流。

