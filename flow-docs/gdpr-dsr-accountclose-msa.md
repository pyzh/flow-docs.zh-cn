---
title: Microsoft 帐户 (MSA) 的 Microsoft Flow GDPR 数据主体帐户关闭请求 | Microsoft Docs
description: 学习使用 Microsoft Flow 来响应 Microsoft 帐户的 GPDR 数据主体帐户关闭请求。
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
ms.openlocfilehash: 268e6039b4f2dbb43522fd07b1120d8c4256e9af
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34562938"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>响应 Microsoft Flow 的 GDPR 数据主体帐户关闭请求

个人数据的“删除权限”是 GDPR 中的关键保护。 此权限包括删除所有个人数据（审核日志信息除外）。 当用户决定关闭其 Microsoft 帐户 (MSA) 时，还将删除用户的基础数据。

以下资源包含用户在关闭 MSA 时将自动删除的个人数据：

|包含个人数据的资源|
|------|
|产品和服务活动|
|运行历史记录|
|流|
|活动源|
|用户详细信息|
|连接|

## <a name="account-close-requests"></a>帐户关闭请求

下面的步骤介绍了如何为 GDPR 的帐户关闭请求提供自助服务。

1. 使用 Microsoft 帐户登录到 [Microsoft 帐户关闭门户](http://go.microsoft.com/fwlink/?LinkId=523898)，然后选择“下一步”。

    > [!NOTE]
    > 将提醒你取消现有订阅或将数据从现有服务导出到可能已订阅的服务。
    >
    >

    ![取消订阅](./media/gdpr-dsr-delete-msa/accountclose.png)

1. 确认了解关闭 MSA 所造成的影响，然后选择“将帐户标记为关闭”。

    此时将显示一条通知，指示将在 30 天内关闭帐户。 你可在此 30 天内随时重新开启此帐户。

    ![帐户已关闭](./media/gdpr-dsr-delete-msa/accountclosed.png)

    在此 30 天的时间窗口结束时，将开始删除此 MSA 的所有 Microsoft Flow 资源的过程。

## <a name="learn-more"></a>了解详情

* [Microsoft Flow](getting-started.md) 入门
* 了解 Microsoft Flow 的[新增功能](release-notes.md)
