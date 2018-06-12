---
title: Microsoft 帐户 (MSA) 的 Microsoft Flow GDPR 数据主体导出请求 | Microsoft Docs
description: 了解如何使用 Microsoft Flow 来响应 Microsoft 帐户的 GPDR 数据主体导出请求。
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
ms.openlocfilehash: 6c1bf3038020f56e5eae57e345391ace2fe65d7f
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34562949"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>响应 Microsoft Flow 的 GDPR 数据主体导出请求

为了在你使用一般数据保护条例 (GDPR) 的过程中与你一同协作，我们开发了帮助你进行准备工作的文档。 该文档不仅介绍了我们为 GDPR 所做的准备工作，还分享了有关在 Microsoft 中使用 Microsoft Flow 时如何支持 GDPR 符合性的步骤示例。

## <a name="manage-export-requests"></a>管理导出请求

数据可移植性权限允许数据主体请求电子格式（即“结构化、常用、计算机可读和可交互格式”）的个人数据副本，数据主体可能会将该副本传输给其他数据控制者。

使用 [Microsoft 隐私仪表板](https://account.microsoft.com/privacy/)或 [Microsoft Flow](https://flow.microsoft.com/) 查找或导出特定用户的个人数据。

|个人数据|位置|
|-----------------|-------------------|
|产品和服务活动|Microsoft 隐私仪表板|
|流|Microsoft Flow Maker 门户|
|运行历史记录|Microsoft Flow Maker 门户|
|活动源|Microsoft Flow Maker 门户|
|连接|Microsoft Flow Maker 门户|

## <a name="export-product-and-service-activity"></a>导出产品和服务活动

1. 使用 Microsoft 帐户 (MSA) 登录到 [Microsoft 隐私仪表板](https://account.microsoft.com/privacy/)。
1. 选择“活动历史记录”。

    ![活动历史记录](./media/gdpr-dsr-export-msa/activityhistory.png)可浏览所使用的不同 Microsoft 应用程序和服务的活动历史记录。
1. 若要导出“产品和服务活动”数据，请选择“下载数据”，然后选择“创建新存档”。

    ![下载数据](./media/gdpr-dsr-export-msa/downloaddata.png)

1. 选择“应用和服务使用情况”，然后选择“创建存档”。

    ![下载数据](./media/gdpr-dsr-export-msa/create-archive.png)
1. 已创建新的存档。 选择“下载”获取导出的产品和服务活动数据。

    ![下载](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>导出流

有权访问流的最终用户可通过执行以下步骤导出流：

1. 登录到 [Microsoft Flow](https://flow.microsoft.com/)。

1. 选择“我的流”，然后选择要导出的流。

1. 选择“...更多”，然后选择“导出”。

    ![导出流](./media/gdpr-dsr-export/export-flow.png)

1. 选择“包(.zip)”。

现在，你的流将以压缩包的形式提供给你。 有关详细信息，请参阅有关[如何导出和导入流](https://flow.microsoft.com/blog/import-export-bap-packages/)的博客文章。

## <a name="export-run-history"></a>导出运行历史记录

运行历史记录包括流的所有运行列表。 此数据包括流的状态、开始时间、持续时间以及触发器和操作的输入/输出数据。

有权访问流的最终用户可通过执行以下步骤导出此数据：

1. 登录到 [Microsoft Flow](https://flow.microsoft.com/)。
1. 选择“我的流”链接，然后选择想要导出运行历史记录的流。
1. 在“运行历史记录”窗格中，选择“查看所有”。

    ![运行历史记录](./media/gdpr-dsr-export/run-history.png)

1. 选择“下载 CSV”。

    ![下载 CSV](./media/gdpr-dsr-export/download-csv.png)

运行历史记录下载为 .csv 文件，方便在 Microsoft Excel 或文本编辑器中打开，以分析结果。

## <a name="export-a-users-activity-feed"></a>导出用户的活动源

在 [Microsoft Flow](https://flow.microsoft.com/) 中，活动源显示用户的活动、失败和通知的历史记录。 用户可通过执行以下步骤来查看其活动源：

1. 登录到 [Microsoft Flow](http://flow.microsoft.com/)，选择右上角旁的钟形图标，然后选择“显示所有活动”。

    ![显示活动源](./media/gdpr-dsr-export/show-activity-feed.png)

1. 在“活动”屏幕中，复制结果，然后将其粘贴到文本编辑器（如 Microsoft Word）中。

    ![显示活动源](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>导出用户的连接

连接允许流连接到 API、SaaS 应用程序和其他第三方系统。 请按照以下步骤来查看你的连接：

1. 登录到 [Microsoft Flow](http://flow.microsoft.com/)，选择右上角旁的齿轮图标，然后选择“连接”。

    ![显示连接](./media/gdpr-dsr-export/show-connections.png)
1. 复制结果，然后将其粘贴到文本编辑器（如 Microsoft Word）中。
