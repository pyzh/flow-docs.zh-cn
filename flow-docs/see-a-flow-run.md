---
title: 观看流运行 | Microsoft Docs
description: 查看流的每一步的输入和输出，确保其表现正常。
services: ''
suite: flow
documentationcenter: na
author: merwanhade
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/05/2018
ms.author: mhade
ms.openlocfilehash: 224bc75a1025d024af236536f4325d2c577e248c
ms.sourcegitcommit: d00c10759d4afb54517a0b1032f8d0a509006d5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="watch-your-flows-in-action"></a>观看运行中的流

>[!VIDEO https://www.youtube.com/embed/3wPoUCGm7Yg]

为了确保流正常运行，请执行触发器，然后查看流中每一步所生成的输入和输出。

1. 创建或更新流，然后在选择“创建流”或“更新流”后，让设计器保持打开状态。

     例如，[创建一个流](get-started-logic-flow.md)，只要有人使用 **#azure** 井号标签发送推文，就让系统发送电子邮件。
1. 为流执行启动操作。

    例如，发送包含 **#azure** 哈希标记的推文。

    启动操作以及随后的每个步骤都会指示该操作是否成功，以及所花费的时间。

    ![“成功运行”的图像](./media/see-a-flow-run/successful-flow-run.png)
1. 选择触发器或操作，查看其输入和输出。

    ![“带扩展卡的成功运行”的图像](./media/see-a-flow-run/successful-flow-expanded-cards.png)
1. 选择“编辑流”进行更多的更改，或者选择“完成”（如果流正常运行）。
