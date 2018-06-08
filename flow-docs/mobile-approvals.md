---
title: 在移动设备上审批请求 | Microsoft Docs
description: 使用移动设备审批在 Microsoft Flow 中创建的请求。
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
ms.date: 07/20/2017
ms.author: deonhe
ms.openlocfilehash: 2b856dfa75e0acb7eb83525c4d64d070315b5735
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440183"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>在移动设备上使用 Microsoft Flow 审批请求
如果某个流将你标识为审批者，并且你已安装用于 Microsoft Flow 的移动应用，则每当系统请求你进行审批时，你就会收到推送通知。

本文演示了几个常见的情形，当你在用于 Microsoft Flow 的移动应用中管理审批请求时，可能会遇到这些情形。

> [!NOTE]
> 本主题中的图片来自 Android 设备，但 iOS 上的体验是类似的。
> 
> 

## <a name="prerequisites"></a>先决条件
若要完成本演练，你需要：

* 一个运行用于 Microsoft Flow 的移动应用的 [Android](https://aka.ms/flowmobiledocsandroid) 或 [iOS](https://aka.ms/flowmobiledocsios) 设备。
* 被指定为审批流中的审批者。
* 待审批的请求。

## <a name="view-pending-requests"></a>查看待处理的请求
1. 打开用于 Microsoft Flow 的移动应用。
   
    ![启动移动应用](./media/mobile-approvals/open-app.png)
2. 选择右上角的“审批”。
   
    ![选择“审批”](./media/mobile-approvals/select-approvals.png)
3. 查看所有挂起的审批：
   
    ![查看待审批请求](./media/mobile-approvals/show-pending-approval-requests.png)

如果没有任何待审批请求，请创建一个[审批流](modern-approvals.md)，将自己设置为审批者，然后触发该流。 在该流触发并发送待审批请求后数秒钟，审批请求就会出现在审批中心。

## <a name="approve-requests-and-leave-an-optional-comment"></a>审批请求并根据需要留下注释
1. 如果尚未这样做，请按照上述步骤[查看挂起的请求](mobile-approvals.md#view-pending-requests)。
2. 在要批准的请求上选择“批准”。
   
    ![选择“批准”](./media/mobile-approvals/select-approve.png)
3. （可选）选择“添加注释(可选)”。
   
    ![选择“添加注释”](./media/mobile-approvals/select-add-comment.png)
   
    在“添加注释”屏幕上输入注释。
   
    ![输入注释](./media/mobile-approvals/enter-comment-for-approval.png)
4. 在右上角选择“确认”。
   
    ![确认已完成](./media/mobile-approvals/tap-confirm-button.png)
   
    流记录你的决策后，会显示成功屏幕。
   
    ![成功屏幕](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>拒绝请求并根据需要留下注释
执行[审批请求的步骤](mobile-approvals.md#approve-requests-and-leave-an-optional-comment)，但在第二步选择“拒绝”。

## <a name="learn-more"></a>了解详情
[创建新式审批流](modern-approvals.md)。

