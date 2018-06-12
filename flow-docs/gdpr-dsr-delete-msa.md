---
title: Microsoft 帐户 (MSA) 的 Microsoft Flow GDPR 数据主体删除请求 | Microsoft Docs
description: 了解如何使用 Microsoft Flow 来响应 Microsoft 帐户的 GPDR 数据主体删除请求。
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
ms.openlocfilehash: c7bede08503fc1c009f07201f98e1a2197251bda
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34562945"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>响应 GDPR 数据主体删除请求

删除个人数据的“删除权限”是 GDPR 中的关键保护。 删除个人数据包括删除所有个人数据（审核日志信息除外）。

通过 Microsoft Flow，用户可生成自动化工作流。 当用户决定删除 Microsoft Flow 中的个人数据时，可检查个人数据，并确定删除部分数据还是全部数据。

下表显示了哪些个人数据将自动删除，以及哪些数据需要 Microsoft 帐户 (MSA) 用户检查和删除。

|要求 MSA 用户检查和删除|自动删除|
|------|------|
|产品和服务活动|运行历史记录|
|流|活动源|
|连接||

Microsoft Flow 提供以下体验，帮助用户查找、检查或更改未自动删除的个人数据和资源：

## <a name="manage-delete-requests"></a>管理删除请求

下面的步骤介绍如何为 GDPR 的删除请求提供自助服务。

### <a name="delete-product-and-service-activity"></a>删除产品和服务活动

1. 使用 MSA 登录到 [Microsoft 隐私仪表板](https://account.microsoft.com/privacy/)。
1. 选择“活动历史记录”链接。

    ![活动历史记录](./media/gdpr-dsr-export-msa/activityhistory.png)

1. 可搜索或浏览所使用的不同 Microsoft 应用程序和服务（包括 Microsoft Flow）的活动历史记录。 选择“删除”，删除特定产品或服务活动事件。

    ![删除事件](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. 在几分钟内从隐私仪表板中删除此项。

### <a name="list-and-delete-flows"></a>列出和删除流

用户可按照以下步骤从 [Microsoft Flow](https://flow.microsoft.com) 中列出和删除流：

1. 登录到 [Microsoft Flow](https://flow.microsoft.com)，然后在“我的流”上选择流。

1. 选择要删除的流旁边的“...”，然后选择“删除”。

    ![删除事件](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>删除连接

连接器使用连接与 API 和 SaaS 系统通信。 连接包含对创建连接的用户的引用。 用户可按照以下步骤随时删除这些引用：

1. 登录到 [Microsoft Flow](https://flow.microsoft.com)，选择齿轮图标，然后选择“连接”。

    ![删除事件](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. 选择要删除的连接，选择“...”，然后选择“删除”。

    ![删除事件](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. 选择确认提示上的“删除”图标。

    ![删除事件](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> 如果其他流使用要删除的连接，则将通知你需要新连接。 否则，选择“删除”，继续进行操作。
>
>

## <a name="learn-more"></a>了解详情

* [Microsoft Flow](getting-started.md) 入门
* 了解 Microsoft Flow 的[新增功能](release-notes.md)
