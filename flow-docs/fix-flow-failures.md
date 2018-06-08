---
title: 流故障排除 | Microsoft Docs
description: 排查发生流故障的部分最常见原因
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/17/2017
ms.author: stepsic
ms.openlocfilehash: 7f4e41437fa19f58c08e2ecd1fb65a3a30092ef8
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439535"
---
# <a name="troubleshooting-a-flow"></a>流故障排除
## <a name="identify-the-error"></a>识别错误
在修复流故障之前，必须确定流故障的原因。 单击或点击 Web 门户顶部的通知图标（或打开移动应用中的“活动”选项卡），然后单击或点击列表中显示的流。

![通知](./media/fix-flow-failures/notifications-toolbar.png)

将会显示流的详细信息，至少一个步骤会显示红色叹号图标。 打开该步骤，查看错误消息。

![错误消息](./media/fix-flow-failures/flow-run-failure.png)

## <a name="authentication-failures"></a>身份验证故障
在许多情况下，流故障的原因是身份验证错误。 如果属于此类错误，则错误消息会包含“未授权”，或者会显示错误代码 **401** 或 **403**。 通常可以通过更新连接来修复身份验证错误：

1. 在 Web 门户顶部，单击或点击齿轮图标打开“设置”菜单，然后单击或点击“连接”。
2. 滚动到你看到“未授权”错误消息的连接。
3. 在连接旁边，单击或点击关于连接未进行身份验证的消息中的“验证密码”链接。
4. 按照显示的说明验证凭据，返回到流运行故障处，然后单击或点击“重新提交”。
   
    流现在应正常运行。

## <a name="action-configuration"></a>操作配置
如果流操作中的设置无法正常运行，流也会发生故障。 在这种情况下，错误消息会包含“请求错误”或“找不到”，或者会显示错误代码 **400** 或 **404**。

错误消息会指定如何纠正故障。 需单击或点击“编辑”按钮，然后更正流定义内的问题。 保存更新的流，然后单击或点击“重新提交”，尝试再次使用更新的配置运行。

## <a name="other-failures"></a>其他故障
如果显示错误代码 **500** 或 **502**，则表明故障是临时的或暂时的。 单击或点击“重新提交”，再次尝试该流。

如果遇到其他问题，[请咨询我们的社区](https://go.microsoft.com/fwlink/?LinkID=787467)，因为其他人可能遇到过类似的问题。

