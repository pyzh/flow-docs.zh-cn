---
title: 了解 Microsoft Flow 环境 | Microsoft Docs
description: 了解如何使用环境来隔离流
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
ms.openlocfilehash: e6667c1c1999c36177d40d52fa657edadd063516
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "31008302"
---
# <a name="choosing-an-environment"></a>选择环境

本文介绍 Microsoft Flow 的**环境**，你可以在其中创建和安全隔离流、网关、连接和其他资源。

本文内容：

* 环境提供的功能。
* 在环境之间切换。
* 如何在正确的环境中创建流。

## <a name="environments-overview"></a>环境概述

创建某个流时，可以选择托管该流的环境以及该流使用的资源。 可以根据不同的方案使用不同的环境。

## <a name="here-are-a-few-scenarios-for-using-environments"></a>下面是使用环境的几种方案

方案|建议
-----|-----
需要创建一个使用 Microsoft Common Data Service 连接的流。|将流和 Common Data Service 放入同一环境。 这可确保所有数据都在这种环境（隔离边界）中进行隔离。
需要为人力资源部创建流。 用户想要确保只有人力资源部门的用户能访问该流。|创建一个环境并只在其中添加人力资源用户。 将流和流使用的其他任何资源放入此环境。
欧洲的用户需要使用流来显示 SharePoint 数据。|在欧洲创建一个环境，然后在其中创建流和 SharePoint 连接。 此欧洲环境可为欧洲用户提供最佳性能，因为所有资源都在欧洲本地（数据地域化）。

只有 Microsoft Flow 管理员才能创建环境。 管理员可以控制谁有权访问环境。 有关如何创建和管理环境的详细信息，请参阅[管理环境](environments-overview-admin.md)主题。

## <a name="switching-environments"></a>切换环境

可以通过 Microsoft Flow 在环境之间轻松进行切换。 切换环境时，只能查看在该特定环境中创建的项，而无法查看或访问其他环境中的项。

下面是一个示例。

在“人力资源”环境中创建名为 *NewEmployee* 的流。 在 [Microsoft Flow](https://flow.microsoft.com) 中，打开“销售”环境。 *NewEmployee* 流未列出。 若要查看“NewEmployee”流，请打开“人力资源”环境。 请记住，同样的规则适用于在该环境中创建的其他任何项，包括连接、网关、流，等等。

遵循以下步骤切换环境：

1. 登录到 [Microsoft Flow](https://flow.microsoft.com)。
1. 在右上角，可以看到代表你的个人档案的图像。

   ![个人档案图像](./media/environments-overview-maker/default-environment.png)

1. 选择该图像。 此时，一个下拉列表会显示所有可用的环境。 当前已登录的环境已被选中：

   ![环境图像列表](./media/environments-overview-maker/all-environments.png)
1. 若要切换到另一环境，请在列表中选择该环境：

   ![选择要切换到的环境](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow 会切换到新环境。

## <a name="create-flows-in-the-right-environment"></a>在正确的环境中创建流

创建流之前，请选择要将流及其资源添加到的环境。

> [!NOTE]
> 如果在错误的环境中创建了流，则需要将其删除，然后在正确的环境中创建。

选择用于托管流的环境时，请考虑以下因素：

* 只能在默认环境中创建网关。 因此，若要使用网关将流连接到本地数据，则需要使用默认环境。
* Microsoft Common Data Service 数据库已绑定到特定的环境。 因此，若要创建使用 Common Data Service 的流，必须在托管该数据库的环境中创建该流。
* 将会显示可在其中编辑资源的所有环境。 但是，需要请求管理员将你作为创建者添加到要在其中创建流的所有环境。

> [!NOTE]
> 始终可以在默认环境中创建流。

## <a name="next-steps"></a>后续步骤

* [通过模板创建流](get-started-logic-template.md)
* [创建流](get-started-logic-flow.md)
* [面向管理员的环境概述](environments-overview-admin.md)