---
title: 创建自定义连接器和嵌入流 | Microsoft Docs
description: 创建自定义连接器，执行共享、嵌入流等操作。
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: barathb
ms.openlocfilehash: a3f1e21cfbf00749a0ef09c0363da162f0419f42
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439697"
---
# <a name="start-to-build-with-microsoft-flow"></a>开始使用 Microsoft Flow 进行生成

可通过以下方法使用 Microsoft Flow 扩展应用程序：

* 创建自定义连接器并进行连接。
* 与所有 Microsoft Flow 用户共享自定义连接器。
* 在应用内嵌入流体验。
* 突出显示所有自定义连接器，使用户能够以最适合自己的方式与 Microsoft Flow 交互。

## <a name="prerequisites"></a>先决条件

* [Microsoft Flow](https://flow.microsoft.com) 帐户。

## <a name="create-a-custom-connector"></a>创建自定义连接器

如果希望通过 Microsoft Flow 连接到 Web 服务，首先需创建自定义连接器。 注册自定义连接器时，需将 Web 服务的特征告知 Microsoft Flow，这些特征包括：所需身份验证、所支持的触发器和操作，以及每项此类操作的参数和输出。

遵循此教程的说明，了解如何[注册和使用自定义连接器](https://powerapps.microsoft.com/tutorials/register-custom-api/)。 注册自定义连接器后，可在组织内共享该连接器进行测试。

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>与所有 Microsoft Flow 用户共享自定义连接器

完全测试自定义连接器后，启动[审核进程](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/)，获得 Microsoft 审批，从而与所有其他 Microsoft Flow 用户共享。

审核进程需要以下内容：

* 一个 OpenAPI 文件，代表 API 以及任何身份验证信息。
* 连接器图标。
* 连接器说明。
* 大约 10 项建议，说明其他用户如何通过模板从连接器中受益。

提交此信息后，Microsoft 就会开始在 Microsoft Flow 和 Microsoft PowerApps 中评估用户 API 的功能。

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>在网站或应用中嵌入流体验

在应用内[嵌入](embed-flow-dev.md) Microsoft Flow，以便在应用和 Microsoft Flow 支持的所有其他服务之间进行深入的上下文集成。 例如，可以执行以下操作：

* 浏览与服务相关的所有模板，让用户选择一个模板。
* 管理用户拥有的与应用相关的流。

## <a name="next-steps"></a>后续步骤

了解如何在应用内[嵌入](embed-flow-dev.md) Microsoft Flow。
