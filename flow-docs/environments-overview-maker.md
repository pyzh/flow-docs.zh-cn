---
title: "在创建 Microsoft Flow 时切换环境 | Microsoft Docs"
description: "创建者如何在创建 Microsoft Flow 时使用不同的环境"
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: bcbb566c20291da14881d771c538dd89689b6b1d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="choosing-an-environment"></a>选择环境
使用 Microsoft Flow，用户可以在不同的环境中工作，并可以在这些环境之间轻松切换。 本文的范围涵盖环境的下列主题：

* 提供环境的背景
* 切换环境
* 如何在正确的环境中创建流

## <a name="environments-overview"></a>环境概述
环境会为用户的流、连接、网关和其他资源提供隔离边界。 在创建流时，可以选择托管流的环境及该流所使用的资源。 用户可以在不同的情况下使用不同的环境。

示例如下：

* 用户需要创建使用到 Microsoft 通用数据服务的连接的流。 在这种情况下，流和通用数据服务在同一环境中。 这可确保所有数据都在这种环境（隔离边界）中进行隔离。
* 用户要为人力资源部门创建流。 用户想要确保只有人力资源部门的用户能访问该流。 例如，用户不想让销售组使用该流。 在这种情况下，可以使用一个独立的环境，仅人力资源部门用户具有该环境的权限，以托管该流及该流使用的所有资源，包括网关或连接。
* 有欧洲用户使用流来显示 SharePoint 数据。 在这种情况下，在欧洲创建一个托管该流和 SharePoint 连接的环境。 此欧洲环境可为欧洲用户提供最佳性能，因为所有资源都在欧洲本地（数据本地化）。

环境由 Microsoft Flow 管理员创建。 这些管理员还控制哪些用户有权访问不同的环境。

本主题介绍如何在不同环境之间导航。 有关如何创建并管理环境的详细信息，请参阅[管理员环境](environments-overview-admin.md)。

## <a name="switching-environments"></a>切换环境
可以通过 Microsoft Flow 在环境之间非常轻松地进行切换。 进行切换时，可以看到该特定环境中的所有项目，看不到任何其他环境中的项目。

下面是一个示例。

在“人力资源”环境中创建名为“NewEmployee”的流。 在 [flow.microsoft.com](http://flow.microsoft.com) 中，请打开“销售”环境。 “NewEmployee”流未列出。 若要查看“NewEmployee”流，请打开“人力资源”环境。 请记住，这适用于在该环境中创建的任何项目，包括连接、网关、PowerApps 等。

1. 打开 [flow.microsoft.com](http://flow.microsoft.com)。
2. 用户在右上角可以看到自己的名称以及所在的环境：  
   ![](./media/environments-overview-maker/default-environment.png)
   
    请注意图中的通知。 这些通知是特定于此默认环境中的流。
3. 选择名称。 在下拉列表中，列出了所有可供用户使用的环境。 用户当前的环境已选中：  
   ![](./media/environments-overview-maker/all-environments.png)
4. 若要切换到另一环境，请在列表中选择该环境：  
   ![](./media/environments-overview-maker/select-europe.png)
5. Microsoft Flow 自动切换到新环境：  
   ![](./media/environments-overview-maker/europe-environment.png)
   
    请注意，图中没有通知。 新的欧洲环境没有通知。

## <a name="create-flows-in-the-right-environment"></a>在正确的环境中创建流
在创建流之前，务必确保选择用户想要流所在的环境。 否则，用户将需要删除流并在正确的环境中重新创建流。

在选择创建流的环境时，请考虑以下因素：

* 在默认环境中创建网关。 无法在其他环境中创建网关，因此，如果用户想要连接到本地数据，将需要使用默认环境。
* 流只能使用连接和同一环境中的其他资源。 无法使用其他环境中的资源。 例如，你要创建使用自定义连接器的流。 此自定义连接器必须与该流位于同一环境中。
* Microsoft 通用数据服务数据库始终绑定到一个环境。 这意味着如果用户想要使用通用数据服务数据，必须选择数据库所在的环境。
* 用户将看到用户可以在其中编辑资源的所有环境。 但是，这并不意味着用户可以在所有环境中创建新资源。 因此，在某些环境中，用户可能无法创建新流。 用户需要请求管理员将其作为“创建者”添加到该环境中，或者，选择不同的环境来创建流 （用户将始终能够在默认环境中创建流）。  

## <a name="what-you-did"></a>用户进行的操作
使用以下步骤，用户可以在其有权使用的环境之间进行切换。 现在，开始创建流。

## <a name="next-steps"></a>后续步骤
[通过模板创建流](get-started-logic-template.md)  
[创建流](get-started-logic-flow.md)  
[面向管理员的环境概述](environments-overview-admin.md)

