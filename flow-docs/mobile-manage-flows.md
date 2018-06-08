---
title: 通过手机管理流 | Microsoft Docs
description: 查看流的列表、启用或禁用流，以及查看每个流的事件、操作和运行历史记录
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
ms.openlocfilehash: 4a04fec70ae70ff17ddf6e1f93e6461ec432e8d2
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440093"
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>通过手机管理 Microsoft Flow 中的流
查看包含所有已创建流的列表、查看每个流的事件和操作、启用或禁用流，以及浏览其运行历史记录。

**先决条件**

* 在[支持的设备](getting-started.md#use-the-mobile-app)上安装适用于 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows) 的 Microsoft Flow 移动应用。 本主题的图片反映的是 iPhone 版应用，但 Android 和 Windows Phone 上的图片看起来是类似的。
* 如果还没有流，可在 [Microsoft Flow 网站](https://flow.microsoft.com/)上创建一个。 为了方便测试，请使用一个可由用户自行触发的流，这样就不需等待外部事件。

本教程中的流在用户收到特定地址发出的邮件时运行：

![在收到特定地址发出的邮件时触发流](./media/mobile-manage-flows/create-trigger.png)

当流能够实际使用时，可以使用个人的测试用电子邮件地址以及一个其他地址（例如，用户经理的地址）来配置此类流。

在运行时，流会使用以下语法向用户的手机发送自定义推送通知：

![将消息发送到 Slack](./media/mobile-manage-flows/create-event.png)

**注意**：也可通过移动应用[监视流活动](mobile-monitor-activity.md)。

## <a name="manage-a-flow"></a>管理流
1. 打开移动应用，然后在屏幕底部点击“我的流”列出所有流。
   
    每个条目都会显示流的名称、其事件和操作的图标、最近运行的时间，以及一个指示最近的运行是否成功的图标。
   
    ![流列表](./media/mobile-manage-flows/flow-list.png)
2. 点击流即可显示其管理选项。
   
    ![管理流的选项](./media/mobile-manage-flows/flow-details.png)
3. 点击“启用流”开关即可启用或禁用流。
4. 点击“查看流”显示该流的事件和操作，点击每个事件或操作将其展开，然后点击“后退”。
   
    ![流的事件和操作](./media/mobile-manage-flows/flow-event-action.png)
5. 点击“运行历史记录”即可显示流的成功和/或失败情况。
   
    ![运行列表](./media/mobile-manage-flows/history-mixed.png)
6. 点击一个运行即可显示每个事件和操作是否成功，以及在成功的情况下所花费的时间（以秒为单位）。
   
    ![运行详细信息](./media/mobile-manage-flows/flow-run.png)

