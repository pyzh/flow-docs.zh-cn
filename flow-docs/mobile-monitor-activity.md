---
title: 通过手机监视活动 | Microsoft Docs
description: 查看每个流的成功/失败次数、每个运行的发生时间，以及所耗费的时间
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
ms.openlocfilehash: a9318a1571d46635babbb0b061ff65734ad172fe
ms.sourcegitcommit: f0202f74ba9a2282a670a1751462f598a5ea0ce5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>通过手机监视 Microsoft Flow 中的活动
查看汇总情况，了解每个流在今天、昨天以及过去日子里的成功/失败次数。 了解每个运行的详细信息，例如运行时间、每步所花的时间，以及失败情况下的原因。

**先决条件**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* 在[支持的设备](getting-started.md#use-the-mobile-app)上安装适用于 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows) 的 Microsoft Flow 移动应用。 本主题的图片反映的是 iPhone 版应用，但 Android 和 Windows Phone 上的图片是类似的。
* 如果还没有流，可在 [Microsoft Flow 网站](https://flow.microsoft.com/)上创建一个。 为了方便测试，请使用一个可由用户自行触发的流，这样就不需等待外部事件。

本教程中的流在用户收到特定地址发出的邮件时运行：

![在收到特定地址发出的邮件时触发流](./media/mobile-monitor-activity/create-trigger.png)

当流能够实际使用时，可以使用个人的测试用电子邮件地址以及一个其他地址（例如，用户经理的地址）来配置此类流。

在运行时，流会使用以下语法向用户的手机发送自定义推送通知：

![发送推送通知](./media/mobile-monitor-activity/create-event.png)

**注意：** 也可通过移动应用[管理流](mobile-manage-flows.md)。

## <a name="display-a-summary-of-activity"></a>显示活动摘要
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. 如果此前尚未运行流，可触发一个运行来生成数据。
   
    数据显示在应用中可能需要一定的时间。
2. 打开移动应用，其中默认显示“活动”选项卡。
   
    该选项卡按天组织数据，当天的数据在上。
   
    ![按天组织的活动](./media/mobile-monitor-activity/activity-day2.png)
   
    每个条目都会显示流的名称，其图标对应于触发事件和操作。
   
    ![每个流的名称和图标](./media/mobile-monitor-activity/activity-flow-name.png)
   
    如果一天中某个流至少成功运行了一次，则会有一个条目显示成功的次数，以及最近成功运行的时间。 如果流失败，则会有另一个条目显示类似的信息。
   
    ![成功/失败次数摘要](./media/mobile-monitor-activity/activity-summary.png)
   
    如果流发送推送通知，则最近的通知的文本显示在条目底部（如果成功运行）。
   
    ![推送通知示例](./media/mobile-monitor-activity/activity-notification.png)
3. 如果一天中发送了多个推送通知，则对着通知向左轻扫即可查看最多前三轮的通知。 如果一天中发送了四个以上的通知，则可向左轻扫，当“查看更多”出现时即可单击查看包含所有通知的列表。
   
    ![推送通知示例](./media/mobile-monitor-activity/activity-notification-list.png)
4. 点击“返回”回到活动摘要。
5. 若要筛选活动摘要，请点击右上角的图标。
   
    可以显示所有条目，也可以仅显示失败条目，或者仅显示包含推送通知的条目。
   
    ![显示所有运行时，或者仅显示失败，或者仅显示通知](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>显示某个运行的详细信息
1. 在活动摘要中，点击某个条目即可显示最近的运行的详细信息。
   
     每个事件和操作在显示时都有一个图标，表示事件或操作是成功还是失败。 如果成功，则还会显示所花的时间（以秒为单位）。
   
    ![运行的详细信息](./media/mobile-monitor-activity/activity-icons.png)
2. 在屏幕底部，点击“查看以前的运行”列出流的所有运行，然后点击某个运行显示其详细信息。
   
    ![成功/失败历史记录](./media/mobile-monitor-activity/history-mixed.png)

