---
title: 了解如何使用连接和本地数据网关连接到数据 | Microsoft Docs
description: 添加或管理与 SharePoint、SQL Server、OneDrive for Business、Salesforce、Office 365、OneDrive、Dropbox、Twitter、Google Drive 等产品的连接
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
ms.date: 02/15/2017
ms.author: stepsic
ms.openlocfilehash: c0e115732e26bdeb0d7e4c3c60e1aa6c63e0ffc1
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439769"
---
# <a name="manage-connections-in-microsoft-flow"></a>管理 Microsoft Flow 中的连接
如果在 Microsoft Flow 中创建连接，可以在生成流时轻松访问数据。 Microsoft Flow 包含常用连接，其中包括 SharePoint、SQL Server、Office 365、OneDrive for Business、Salesforce、Excel、Dropbox、Twitter 等。 连接与 PowerApps 共享，因此，在一个产品中创建连接时，连接会显示在另一个产品中。

例如，可以使用连接来执行这些任务：

* 更新 SharePoint 列表。
* 从 OneDrive for Business 或 Dropbox 帐户中的 Excel 文件获取数据。
* 在 Office 365 中发送电子邮件。
* 发送推文。

可以采用多种方案创建连接，例如以下方案：

* 创建[基于模板的流](get-started-logic-template.md)
* 创建[基于空白的流](get-started-logic-flow.md)或更新现有流
* 直接在 [Microsoft Flow 网站][1]中创建连接

本主题说明如何在 [Microsoft Flow 网站][1]中管理连接。

## <a name="add-a-connection"></a>添加连接
1. 在 [Microsoft Flow 网站][1]中，使用工作帐户或组织帐户登录。
2. 在右上角附近选择齿轮图标，然后选择“连接”。
   
    ![选择连接](./media/add-manage-connections/connections-menu.png)
3. 选择“创建连接”。
4. 在“可用连接”列表中，选择要设置的连接，例如 SharePoint。
5. 选择“创建连接”按钮，然后输入凭据以设置连接。

设置了连接后，该连接就会在“我的连接”中列出。

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>通过本地数据网关连接到数据
在撰写本文时，SQL Server 和 SharePoint Server 支持本地数据网关。 若要创建使用网关的连接：

1. 按本主题前述步骤添加连接。
2. 在“可用连接”列表中，选择“SQL Server”，然后选择“通过本地数据网关连接”复选框。
   
    ![选择网关](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Microsoft SharePoint 数据网关支持 HTTP 流量，但不支持 HTTPS 流量。
   > 
   > 
3. 提供连接的凭据，然后选择要使用的网关。
   
    有关详细信息，请参阅[管理网关](gateway-manage.md)和[了解网关](gateway-reference.md)。
   
    设置了连接后，该连接就会在“我的连接”中列出。

## <a name="delete-a-connection"></a>删除连接
1. 转到“我的连接”页，然后选择要删除的连接的垃圾桶图标。
   
    ![删除连接](./media/add-manage-connections/delete-connection.png)
2. 选择“确定”以确认要删除连接。
   
    ![确认删除](./media/add-manage-connections/delete-confirmation.png)

删除连接时，连接将从 PowerApps 和 Microsoft Flow 中删除。

## <a name="update-a-connection"></a>更新连接
对于因为帐户详细信息或密码已更改而不起作用的连接，你可以更新该连接。

1. 在“我的连接”页上，选择要更新的连接的“验证密码”链接。
   
    ![验证密码](./media/add-manage-connections/verify-password.png)
2. 出现提示时，请使用新凭据更新连接。

更新连接时，该连接将在 PowerApps 和 Microsoft Flow 二者中更新。

## <a name="troubleshoot-a-connection"></a>排查连接问题
根据组织的策略，可能需要使用相同的帐户登录到 Microsoft Flow 并创建与 SharePoint、Office 365 或 OneDrive for Business 的连接。

例如，你可能会使用 *yourname@outlook.com* 登录到 Microsoft Flow，但在尝试使用 *yourname@contoso.com* 连接到 SharePoint 时被阻止。 可以改为使用 *yourname@contoso.com* 登录到 Microsoft Flow，然后你将能够连接到 SharePoint。

<!--Reference links in article-->
[1]: https://flow.microsoft.com
