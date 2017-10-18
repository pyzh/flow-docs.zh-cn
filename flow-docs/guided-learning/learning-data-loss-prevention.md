---
title: "使用数据丢失防护 (DLP) 策略 | Microsoft Docs"
description: "了解如何通过数据丢失防护策略控制在使用 Microsoft Flow 自动完成任务时，哪些服务可以共享数据。"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: vls4RPVP5xE
courseduration: 6m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 2e69fd07103cb16e6c91476462f39586810b4a5d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="use-data-loss-prevention-dlp-policies"></a>数据丢失防护 (DLP) 策略
随着可用于通过 [Microsoft Flow](https://flow.microsoft.com) 构建工作流的[服务](https://flow.microsoft.com/services)越来越多，你可能需要保护企业服务（例如 SharePoint 或 Salesforce）中存储的敏感业务数据或关键业务数据。 你可能会发现你的组织需要创建策略，以确保敏感业务数据不会发布到 Twitter 和 Facebook 等使用者服务。 使用 Microsoft Flow，可以轻松创建**数据丢失防护** (DLP) 策略，以便严格控制在用户创建流时可与哪些使用者服务共享你的业务数据。  

## <a name="terms-you-should-get-familiar-with"></a>应熟悉的术语
| 术语 | 说明 |
| --- | --- |
| **DLP** |这是“数据丢失防护”的缩写。 你将创建 DLP 策略以管理在**服务**之间共享数据。 |
| **服务** |[服务](https://flow.microsoft.com/services)是 Salesforce、SharePoint 和 Twitter 等应用程序。 这些服务以及其他许多服务用于创建流。 |
| **数据组** |服务的逻辑分组。 你需要将允许共享数据的服务放入同一数据组中。 数据组有两个：“仅业务数据”数据组和“不允许业务数据”数据组。 |
| **环境** |DLP 应用于[环境](../environments-overview-admin.md)。 环境包含用户。 |
| **用户** |用户是 DLP 策略将基于环境中的成员身份应用到的组织成员。 |
| **流** |流是使用可用服务的任意组合的工作流应用。 |

## <a name="all-about-how-dlp-policies-work"></a>有关 DLP 策略工作原理的全部信息
DLP 策略只是一种命名规则，用于将每个服务放入两个互斥数据组之一。 此规则随后会应用到环境。 环境是用户的逻辑分组。 用户不可以创建在你已放入不同数据组中的服务之间共享数据的流。 换言之，你的用户只能创建在**单个**数据组内的服务之间共享数据的流。 不允许跨数据组共享。  

| **数据组名称** | **数据组说明** |
| --- | --- |
| **仅业务数据** |此组中的所有服务都可以在彼此之间共享数据。 它们不能与“不允许业务数据”数据组共享数据。 |
| **不允许业务数据** |此组中的所有服务都可以在彼此之间共享数据。 它们不能与“仅业务数据”数据组共享数据。 |

**注意**：将服务添加到一个数据组会自动将该服务从其他数据组中删除。 例如，如果 Twitter 当前位于“仅业务数据”数据组，并且你不希望允许与 Twitter 共享业务数据，则只需将 Twitter 服务添加到“不允许业务数据”数据组。 这将从“仅业务数据”数据组中删除 Twitter。

## <a name="heres-what-you-need-to-create-a-dlp"></a>下面是创建 DLP 所需满足的条件
* 对 Microsoft Flow [管理中心](https://admin.flow.microsoft.com)的访问权限  
* 环境管理角色中的帐户  
* 一个已分配了用户的环境  

## <a name="create-a-dlp-policy"></a>创建 DLP 策略
以下是如何创建 DLP 策略的简要介绍：  

1. 为策略提供一个名称
2. 选择策略将应用到的环境
3. 将服务添加到两个数据组之一。 请记住，只有位于一个特定组中的服务才可以共享数据，因此，如果创建了任何在位于两个数据组中的服务之间共享数据的流，那么该流在创建者进行保存时都会被自动阻止。  

另外，还有一个有关 DLP 策略的[详细演练](../prevent-data-loss.md)可供使用。  

## <a name="examples"></a>示例
* 如果你打算创建策略，用于将流限制为仅在 SharePoint、Office 365 用户、Office 365 Outlook、OneDrive for Business、Dynamics 365、SQL Server 和 Salesforce 之间共享业务数据，那么你要创建的策略将如下所示：  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* 如果你决定创建一个策略，用于禁止特定环境的任何成员创建共享 SharePoint 数据的流，那么你要创建的策略将如下所示。 请注意，SharePoint 是“仅业务数据”数据组中的唯一服务：  
  ![仅业务数据](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

