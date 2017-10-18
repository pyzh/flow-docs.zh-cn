---
title: "基于电子邮件属性运行流。 | Microsoft Docs"
description: "基于电子邮件的主题、发件人地址或收件人等属性启动流。"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
ms.openlocfilehash: 395cb9bc1d58e50e5ac8ebac9afaed544f3261ec
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="trigger-a-flow-based-on-email-properties"></a>基于电子邮件属性触发流
使用“收到新电子邮件时”触发器来创建一个流，该流在一个或多个电子邮件属性匹配所提供的条件时运行：

| 属性 | 何时使用 |
| --- | --- |
| Folder |每当特定文件夹收到电子邮件时触发流。 如果有将电子邮件路由到不同文件夹的规则，则此属性会非常有用。 |
| To |基于收件人电子邮件地址触发流。 如果在同一收件箱中收到发送到其他电子邮件地址的电子邮件，则此属性会非常有用。 |
| From |基于发件人电子邮件地址触发流。 |
| Importance |基于所发送电子邮件的重要性触发流。 可以按高重要性、普通重要性或低重要性来发送电子邮件。 |
| Has Attachment |基于传入电子邮件是否存在附件触发流。 |
| Subject Filter |搜索电子邮件主题中是否存在特定字词。 然后流会基于搜索结果运行“操作”。 |

> [!IMPORTANT]
> 每个 [Microsoft Flow 计划](https://flow.microsoft.com/pricing/)都包括一个运行配额。 尽可能地检查流触发器中的属性，这样可以避免不必要地使用运行配额。 如果检查某个条件中的属性，那么每次运行都将记入计划的运行配额，即使未满足定义的筛选器条件。 例如，如果检查某个条件中电子邮件的“发件人”地址，每次运行都将计入计划的运行配额，即使它不是你感兴趣的“发件人”地址。
> 
> 

在下面的演练中，我们可以检查“收到新电子邮件时”触发器中的所有属性。 有关详细信息，请访问[常见计费问题](billing-questions.md#what-counts-as-a-run)和[定价](https://ms.flow.microsoft.com/pricing/)页。

## <a name="prerequisites"></a>先决条件
* 帐户有权访问 [Microsoft Flow](https://flow.microsoft.com)。
* Office 365 Outlook 帐户。
* 适用于 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows) 的 Microsoft Flow 移动应用。
* 与 Office 365 Outlook 和推送通知服务的连接。

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>基于电子邮件主题触发流
在本演练中，我们创建了一个流，如果任何新电子邮件的主题中包含“彩票”一词，它就会向移动电话发送推送通知。 该流随后会将任何此类电子邮件标记为已读。

注意：在本演练发送推送通知期间，用户仍然可以随意使用适合工作流需要的任何其他操作。 例如，可以在 Google 表格或存储在 Dropbox 上的 Microsoft Excel 文件等其他存储库中存储电子邮件内容。

好了，开始操作：

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. 在“主题筛选器”框中，输入流用于筛选传入电子邮件的文本。
   
     在此示例中，我对主题中包含“彩票”一词的任何电子邮件都感兴趣。
   
    ![高级选项](./media/email-triggers/email-triggers-subject-text.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 在收到与先前指定的“主题筛选器”匹配的电子邮件时，输入想要接收的移动通知的详细信息。
   
    ![通知详细信息](./media/email-triggers/email-triggers-4.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. 通过选择页面顶部的“创建流”为流命名，然后进行保存。
   
    ![保存流](./media/email-triggers/email-triggers-subject-notification.png)

祝贺你，在每次收到主题中包含“彩票”一词的电子邮件时，你都将收到推送通知。

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>基于电子邮件的发件人触发流
在本演练中，我们创建了一个流，如果收到任何来自特定发件人（电子邮件地址）的新邮件，它就会向移动电话发送推送通知。 此流随后会将任何此类电子邮件标记为已读。

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. 将发件人的电子邮件地址输入到“发件人”中。
   
     流会对任何发送自该地址的电子邮件执行操作。
   
    ![电子邮件属性](./media/email-triggers/email-triggers-from.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 每当收到先前输入的电子邮件地址发来的邮件时，输入想要收到的移动通知的详细信息。
   
    ![通知详细信息](./media/email-triggers/email-triggers-sender-notification.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. 通过选择页面顶部的“创建流”为流命名，然后进行保存。
   
    ![保存流](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>当特定文件夹收到电子邮件时触发流。
如果有根据地址等某些属性将电子邮件路由到不同文件夹的规则，则可能会想要使用此类型的流。

开始操作：

> [!NOTE]
> 如果还没有将电子邮件路由到收件箱以外的文件夹的规则，请创建此类规则，并通过发送测试电子邮件确认它可以正常工作。
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. 选择已为其创建路由特定电子邮件规则的文件夹。 若要显示所有电子邮件文件夹，请先选择“显示选取器”图标，该图标位于“收到新电子邮件时”卡的“文件夹”框的右侧。
   
    ![选择文件夹](./media/email-triggers/email-triggers-2.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 在先前选择的文件夹收到电子邮件时，输入想要接收的移动通知的详细信息。 如果尚未执行此操作，请输入通知服务的凭据。
   
    ![通知详细信息](./media/email-triggers/email-triggers-folder-notification.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. 通过选择页面顶部的“创建流”为流命名，然后进行保存。
   
    ![保存流](./media/email-triggers/email-triggers-7.png)

通过发送路由到本演练中先前选中文件夹的电子邮件来测试此流。

