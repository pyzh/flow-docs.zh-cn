---
title: "计费和计量问题 | Microsoft Docs"
description: "有关 Microsoft Flow 中计费和计量的常见问题解答"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/21/2016
ms.author: deonhe
ms.openlocfilehash: b627c008e1483360f35b6de579e2c0da32e60c93
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="billing-and-metering-questions"></a>计费和计量问题
本文回答了有关 Microsoft Flow 中计费和计量的常见问题。

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>在哪里可以找到可用定价计划？
请参阅[定价页](https://flow.microsoft.com/pricing/)。

## <a name="where-can-i-find-out-what-my-plan-is"></a>在哪里可以找到我的计划？
请参阅[定价页](https://flow.microsoft.com/pricing/)。

## <a name="how-do-i-switch-plans"></a>如何切换计划？
在顶部导航菜单中，单击或点击“了解”，然后单击或点击“定价”。

![了解 > 定价](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>如何了解我的使用量？
单击或点击“活动”可显示运行记录以及通知和故障。

![“活动”链接](./media/billing-questions/activity-link.png)

如果使用的是免费计划或试用计划，请单击或点击顶部导航栏中的齿轮图标，以针对你的计划显示你当前的使用情况。   

![“设置”按钮](./media/billing-questions/settings.png)

如果使用的不是免费计划或试用计划，则运行次数是针对组织中的所有用户进行了汇总的运行次数。 我们正致力于提供显示整个组织的可用配额和使用情况的功能。

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>如果我的使用量超出限制，会发生什么情况？
Microsoft Flow 可能会开始限制运行。

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>在哪里可以找到有关使用量限制的详细信息？
在[定价页](https://flow.microsoft.com/pricing/)上查看**常见问题**部分。

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>如果执行运行过于频繁，会发生什么情况？
你的计划决定你的流的运行频率。 例如，如果使用的是免费计划，则流可以每 15 分钟运行一次。 如果流在其最近一次运行之后的 15 分钟内被触发，则该流将排队，直到 15 分钟已过去。 查找新数据不算作运行。

## <a name="what-counts-as-a-run"></a>怎样算作运行？
每当触发一个流时，无论是通过自动触发器还是手动启动，都将被视为运行。

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Microsoft 帐户与工作或学校帐户在计费方面是否有差别？
是。 如果使用 Microsoft 帐户（如以 @outlook.com 或 @gmail.com 结尾的帐户）登录，则只能使用免费计划。 若要使用付费计划的功能，则需要使用工作或学校电子邮件 ID 登录。

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>我在尝试升级，但被告知我的帐户不合格。
若要升级，请使用工作或学校帐户，或按照该 [Power BI 文章](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/)中的说明创建 Office 365 试用帐户。

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>为什么我的流只运行了几次，运行次数就用完了？
某些流的运行频率可能高于预期。 例如，你可能会创建一个流，每当你的经理向你发送电子邮件时，该流就会向你发送推送通知。 每次你收到电子邮件（从任何人）时，该流都必须运行，因为该流必须检查电子邮件是否来自于你的经理。 此操作算作一次运行。

用户可以通过将所有所需筛选放到触发器中来解决此问题。 在上面的示例中，请展开“高级选项”菜单，并在“发件人”字段中指定你经理的电子邮件地址。

## <a name="other-limits-and-caveats"></a>其他限制和注意事项
* 每个帐户最多可有：
  * 50 个流
  * 15 个自定义连接器
  * 每个 API 20 个连接，总共不超过 100 个连接。
* 只能在默认环境中安装网关。   
* 某些外部连接器（如 Twitter）实施连接限制以控制服务质量。 当限制生效时，流将失败。 可以通过查看流的运行历史记录中失败的运行来查看此限制的详细信息。

