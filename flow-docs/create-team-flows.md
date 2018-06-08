---
title: 了解如何将其他所有者添加到流并创建团队流 | Microsoft Docs
description: 利用 Microsoft Flow 可以轻松地自动执行重复任务。 可以将用户或组添加为所有者，并与其协作来设计和管理流。
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
ms.date: 04/21/2017
ms.author: deonhe
ms.openlocfilehash: d4e8de2f9f67c07861297e079948a5336ff66e7f
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439679"
---
# <a name="create-team-flows"></a>创建团队流
将他人作为所有者添加到组织中即可创建团队流。 团队流的全部所有者都可以执行以下操作：

* 查看流的历史记录（即，每次运行）。
* 管理流的属性（例如，启动或停止流、添加所有者或更新连接的凭据）。
* 编辑流的定义（例如，添加或删除操作或条件）。
* 添加和删除其他所有者（流的创建者除外）。
* 删除流。

如果你是团队流的创建者或所有者，则会发现流已在 [Microsoft Flow](https://flow.microsoft.com) 的“团队流”选项卡上列出。

![团队流选项卡](./media/create-team-flows/addowner5.png)

> [!NOTE]
> 共享连接**只**能在创建它们的流中使用。
> 
> 

所有者可以使用流中的服务，但不能修改另一个所有者创建的连接的凭据。

## <a name="prerequisites"></a>先决条件
你必须有一个 [Microsoft Flow 付费计划](https://flow.microsoft.com/pricing/)才能创建团队流。 此外，若要添加/删除团队流的所有者，你还必须是创建者或所有者。

## <a name="create-a-team-flow"></a>创建团队流
请按以下步骤创建团队流或将更多所有者添加到团队流。

1. 登录到 [Microsoft Flow](https://flow.microsoft.com)，然后选择“我的流”。
2. 选择想要修改的流的人员图标：
   
    ![团队图标](./media/create-team-flows/addowner1.png)
3. 对于要作为所有者添加的个人或组，请输入个人名称、电子邮件地址或组名称：
   
    ![搜索用户](./media/create-team-flows/addowner2.png)
4. 在显示的列表中，选择想要设为所有者的用户：
   
    ![选择用户](./media/create-team-flows/addowner3.png)
   
     你选择的用户或组将成为流的所有者：
   
    ![新建所有者](./media/create-team-flows/addowner4.png)
   
     恭喜 &mdash; 团队流已创建！

## <a name="remove-an-owner"></a>删除所有者
> [!IMPORTANT]
> 删除某个所有者时，如果其凭据是用于访问 Microsoft Flow 服务的，则应更新相应连接的凭据，使流能够继续正常运行。
> 
> 

1. 选择想要修改的流的人员图标：
   
    ![选择人员图标](./media/create-team-flows/removeowner1.png)
2. 选择想要删除的所有者的“删除”图标：
   
    ![选择删除](./media/create-team-flows/removeowner2.png)
3. 在确认对话框中，选择“删除此所有者”：
   
    ![确认删除](./media/create-team-flows/removeowner3.png)
4. 恭喜 &mdash; 你删除的用户或组不再作为流的所有者列出：
   
    ![用户已删除](./media/create-team-flows/removeowner4.png)

## <a name="embedded-and-other-connections"></a>嵌入连接和其他连接
流中使用的连接划分为两个类别：

* **嵌入** &mdash; 流中使用这些连接。
* **其他** &mdash; 已为流定义了这些连接，但该流中未使用这些连接。

如果停止使用流中的某个连接，该连接将显示在“其他”连接列表中。此列表中将保留该连接，直到所有者再次将该连接包括在此流中。

连接列表显示在流属性的所有者列表下：

![嵌入式连接](./media/create-team-flows/embeddedconnections.png)

