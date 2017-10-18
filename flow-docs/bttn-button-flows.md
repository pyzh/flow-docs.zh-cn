---
title: "使用 bttn 启动流 | Microsoft Docs"
description: "了解如何使用 bttn 启动流"
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
ms.date: 05/30/2017
ms.author: deonhe
ms.openlocfilehash: c4010f95ad2db3c4f3b97b39f0b45934c7b69c48
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>使用 The Button Corporation（预览）中的物理按钮 (bttn) 来运行流
通过按 bttn（[The Button Corporation](https://my.bt.tn/) 生产的物理按钮）来触发流。 例如，可以按 bttn 触发一个流来执行以下任务：

* 联系支持人员获取位置信息
* 向团队发送电子邮件
* 对日历进行分块
* 再订购办公用品

> [!IMPORTANT]
> 必须在[注册](https://my.bt.tn/) bttn 后才能在流中使用它。
> 
> [!TIP]
> 在创建流之前，在 [bttn 网站](https://my.bt.tn/)上配置所有 bttn 属性，例如名称、位置以及电子邮件地址。
> 
> 

还可以通过使用 [Flic 物理按钮](flic-button-flows.md)来触发流。

## <a name="prerequisites"></a>先决条件
* 有权访问 [Microsoft Flow](https://flow.microsoft.com)。
* 至少一个[已注册的 bttn](https://my.bt.tn/)。

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>创建由 Flic 触发的流
在本演练中，我们使用支持人员模板来创建可以通过单次按下 [bttn](https://my.bt.tn/) 触发的流。 流运行时，它将生成支持请求，然后将该请求发送给支持人员。 支持请求为支持人员提供需要帮助的房间位置。 本演练演示如何从模板中创建此流，但是还可以使用空白模板，这样用户能够完全控制流的各个方面。

可以使用任何这些模板为 bttn 快速创建流并连接到 Zendesk、Google 和 SharePoint 等：

![bttn 模板](./media/bttn-button-flows/bttn-templates.png)

提示：出于本演练的目的，请对 bttn 命名，该名称表示典型办公楼中的会议室。

bttn 的设置应类似于以下示例（摘自 bttn 网站）：

![bttn 模板](./media/bttn-button-flows/bttn-config.png)

现在，你已注册并配置 bttn，让我们开始创建流。

### <a name="sign-in-and-select-a-template"></a>登录并选择模板
1. 登录到 [Microsoft Flow](https://flow.microsoft.com)。
   
    ![登录](./media/bttn-button-flows/sign-into-flow.png)
   
    注意：可以在适用于 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows) 的 Microsoft Flow 移动应用中创建流，作为一种替代。
2. 在搜索栏中输入“bttn”，然后选择搜索图标。
   
    ![搜索](./media/bttn-button-flows/bttn-search-template.png)
   
    选择“搜索”图标后，将显示可用于 bttn 的所有模板。
3. 选择“使用 Bttn 调用会议室的技术支持”模板。
   
    ![支持模板](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>授权 Microsoft Flow 连接到 bttn
1. 如果系统提示，请登录到 bttn 和 Office 365 Outlook 服务，以启用“继续”按钮。
   
    ![凭据](./media/bttn-button-flows/bttn-provide-credentials.png)
2. 登录到 bttn 服务时，授权 Microsoft Flow 使用 bttn。
   
    重要说明：如果未授权 Microsoft Flow 使用 bttn，则无法从 Microsoft Flow 查看或连接到它们。
   
    ![授权](./media/bttn-button-flows/authorize-bttn.png)
3. 登录到这两个服务后，选择“继续”。
   
    ![继续](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>选择触发流的 bttn
1. 在“按下 bttn 时”卡上，打开 bttn ID 列表，然后选择想要使用的 bttn。
   
    ![选择 bttn](./media/bttn-button-flows/bttn-id.png)
   
    流现在应类似于以下示例。
   
    ![流概览](./media/bttn-button-flows/bttn-done.png)
2. 给流命名，然后选择“创建流”进行保存。
   
    ![保存流](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>测试流并确认结果
1. 按 bttn 上的按钮。
2. 查看流的运行历史记录，以确认它已成功运行。
   
    可以在 Microsoft Flow 网站或移动设备上查看运行历史记录。
   
    注意：在支持请求电子邮件中选择“确认”之前，运行状态设置为“正在运行”。
3. 还可以确认电子邮件已发送给支持团队。
   
    如果已按照步骤执行操作，支持电子邮件将类似于以下示例：
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>故障排除
* 如果流尚未触发，则登录到 The Button Corporation 的站点，并确认是否已记录按钮活动（按下）。
* 此外，还可以深入了解 Microsoft Flow 站点上的运行活动，并检查错误消息。

## <a name="more-information"></a>详细信息
* [共享按钮流](share-buttons.md)。
* 了解如何在按钮流运行时使用[按钮触发器令牌](introduction-to-button-trigger-tokens.md)发送当前数据。
* [安装适用于 Android 的 Microsoft Flow 应用](https://aka.ms/flowmobiledocsandroid)。
* [安装适用于 iOS 的 Microsoft Flow 应用](https://aka.ms/flowmobiledocsios)。

