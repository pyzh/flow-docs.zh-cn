---
title: 通过 Flic 按钮启动流 | Microsoft Docs
description: 通过 Flic by Shortcut Labs 提供的物理按钮轻松启动按钮流。
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/19/2017
ms.author: deonhe
ms.openlocfilehash: 518834103c1a17ef2f5af218eae43ccab4e5fda2
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440831"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>通过按 Flic 智能按钮（预览版）运行流
通过按 Shortcut Labs 提供的名为 Flic 的物理按钮来触发流。 例如，可以通过按 Flic 来跟踪工作时间、阻止日历、对某个事件的访问者计数，或者保存地理位置。

> [!IMPORTANT]
> 在创建流之前，请使用 Flic 的 [Android](https://play.google.com/store/apps/details?id=io.flic.app) 或 [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) 版移动应用配置所有 Flic 属性。
> 
> 

## <a name="prerequisites"></a>先决条件
若要将 Flics 与 Microsoft Flow 配合使用，必须符合以下条件：

* 有权访问 [Microsoft Flow](https://flow.microsoft.com)。
* 已下载 Flic 的 [Android](https://play.google.com/store/apps/details?id=io.flic.app) 或 [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) 移动应用，并通过其完成了一个或多个 Flic 的配对。

## <a name="configure-flic-properties"></a>配置 Flic 属性
使用 Flic 的移动应用对 Flic 的事件编程。 这些事件是：

* 单击（快按一次）
* 双击（快按两次）
* 按住（长按一次）

此屏幕截图以示例方式演示了 Flic 配置过程：

![配置 Flic](./media/flic-button-flows/configure-flic-actions.png)

将 Flic 事件链接到 Microsoft Flow 以后，即可选择该 Flic 作为流的触发器。 你将在本演练的后面部分选择触发器。

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>创建由 Flic 触发的流
在本演练中，我们使用 Flic 运行一个流，对某个顾问花在每个客户身上的时间进行记录。 该顾问在到达时按 Flic 一次，然后在离开客户时再按一次。 每按一次 Flic 都会运行一次连接到的流。 流将当前时间保存在 Google Sheets 中，然后发送电子邮件通知。 电子邮件包含流运行的详细信息。

注意：请确保已使用 Flic 移动应用进行配对，并配置至少一个用于触发 Microsoft Flow 的“单击”操作。 在此屏幕截图中，我已配置了用于触发 Microsoft Flow 的“单击”操作。 在本演练的后面部分，我们将流配置为按一次（单击）Flic 就触发。

   ![flic 配置](./media/flic-button-flows/flic-configured-for-flow.png)

让我们开始创建流。

### <a name="start-with-a-template"></a>从模块开始
1. 登录到 [Microsoft Flow](https://flow.microsoft.com)。
   
    ![登录](./media/flic-button-flows/sign-into-flow.png)
2. 在搜索栏中输入“flic”，然后选择搜索图标。
   
    ![搜索 flic](./media/flic-button-flows/search-flic.png)
3. 选择“使用 Flic 智能按钮跟踪工作时间”模板。
   
    ![选择模板](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>在 Google Sheets 中创建电子表格
1. 查看模板的详细信息，并请注意，此模板需要 Google Sheets 中的电子表格。
   
   ![查看模板详细信息](./media/flic-button-flows/flic-template-details.png)
2. 在 Google Sheets 中创建一个电子表格，其中包含列名为“ClickType”和“TimeStamp”的工作表。
   
      提示：可以通过在列顶部输入列名来命名 Google Sheets 中的列。 因此，工作表应如以下屏幕截图所示：
   
   ![Google Sheet](./media/flic-button-flows/flic-google-sheet.png)
   
   注意：在本演练后面使用此工作表。

### <a name="add-the-flic-trigger-to-your-flow"></a>将 Flic 触发器添加到流
1. 登录到模板的服务，然后选择“继续”。
   
     登录到模板的所有必需服务后，会启用“继续”。
   
    ![提供凭据](./media/flic-button-flows/flic-template-services-sign-in.png)
2. 在搜索框中输入“flic”，然后选择“Flic - 按 Flic 时”触发器。
   
    ![搜索 flic 触发器](./media/flic-button-flows/flic-search-trigger.png)
3. 从“Flic - 按 Flic 时”卡的“Flic 按钮”列表中选择要使用的 Flic。
4. 从“事件”列表中选择“单击”，表示你希望按一次 Flic 就触发流。
   
    ![选择 flic 操作](./media/flic-button-flows/select-flic.png)
   
   （可选）可以选择“任意”，表示每个 Flic 事件（单击、双击或按住）都可以触发流。
   
   “双击”表示快按 Flic 两次即可触发流。 “按住”表示长按 Flic 即可触发流。
   
   可以随意创建其他流，并使用“事件”列表中的其他事件触发这些流。 例如，可以使用“双击”事件记录离开客户的时间。

### <a name="configure-the-sheet"></a>配置工作表
   在“插入行”卡上，执行以下操作：

1. 从“文件”列表中选择此前创建的电子表格。
2. 从“工作表”列表中选择工作表。
   
   注意：选择工作表后，“插入行”卡上会再显示两个框。 这两个框表示此前创建的工作表中的两个列。
3. 选择“ClickType”框，然后选择“点击类型”令牌。
4. 选择“Timestamp”框，然后选择“点击时间”令牌。
   
    ![配置 Google Sheets 数据](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>确认电子邮件设置正确
1. 确认“向我发送电子邮件通知”卡类似于此屏幕截图。
   
    ![确认电子邮件通知](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>保存并测试流
1. 为流提供名称，然后将其保存。
   
    ![保存流](./media/flic-button-flows/save.png)

如果你一直在按步骤操作，则按 Flic 一次就会触发流。 然后，流会在工作表中记录点击类型和当前时间，并向你发送电子邮件。

1. 按 Flic 一次。
2. 在 Google Sheets 中打开工作表。 此时会看到“ClickType”和“Timestamp”列分别填充了“单击”和时间。
   
    ![查看运行结果](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. 也可通过 Microsoft Flow 网站或 Microsoft Flow 移动应用查看运行结果。 下面是我的测试运行的屏幕截图。
   
    ![保存流](./media/flic-button-flows/flic-test-run-results-portal.png)
4. 下面是我从流运行收到的通知电子邮件正文的样子。
   
    ![保存流](./media/flic-button-flows/flic-email-body.png)

如果你学有余力，还可以考虑扩展流的功能，在按 Flic 时自动记录位置（经纬度）。

## <a name="more-information"></a>详细信息
* [共享按钮流](share-buttons.md)。
* 了解如何在执行按钮流时使用[按钮触发器令牌](introduction-to-button-trigger-tokens.md)发送当前数据。
* 安装适用于 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows) 的 Microsoft Flow 移动应用。

