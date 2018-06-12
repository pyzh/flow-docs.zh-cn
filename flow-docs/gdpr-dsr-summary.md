---
title: GDPR 数据主体请求摘要 | Microsoft Docs
description: 了解如何响应 Microsoft Flow 的 GPDR 数据主体请求。
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
ms.date: 4/24/2018
ms.author: keweare
ms.openlocfilehash: c57296bed460dbf94aa597542413783292e1a8f7
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552159"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>响应 Microsoft Flow 的 GDPR 数据主体请求

本文为你和你的组织准备了欧盟一般数据保护条例 (GDPR)。 本文不仅介绍了 Microsoft 为 GDPR 所做的准备工作，还分享了目前在使用 PowerApps、Microsoft Flow 和 Common Data Service for Apps 时如何支持 GDPR 符合性的步骤示例。

## <a name="prerequisites"></a>先决条件

用户和管理员可以执行本文中概述的操作。

### <a name="users"></a>用户

用户需要具有有效的 Azure Active Directory 帐户和 [Microsoft Flow 许可证](https://preview.flow.microsoft.com/pricing/)。 不满足此要求的用户需要请求管理员来执行这些操作。

### <a name="administrators"></a>管理员

如果使用具有以下两个权限的帐户登录到 [Microsoft Flow 管理中心](https://admin.flow.microsoft.com/)或 [PowerApps 管理员 PowerShell](https://go.microsoft.com/fwlink/?linkid=871804)，则可以执行本文所述的需要管理员权限的操作：

- PowerApps 计划 2 付费或试用许可证。

    [试用许可证](http://web.powerapps.com/trial)在 30 天后过期。

- [Office 365 全局管理员](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504)或 [Azure Active Directory 全局管理员](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)。

### <a name="unmanaged-tenants"></a>非托管租户
如果你是[非托管租户](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover)的成员（即你的 Azure AD 租户没有全局管理员），则仍将能够按照此文章中所述的步骤来导出和删除自己的个人数据。 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>响应 Microsoft Flow 客户数据的 DSR

GDPR 为用户（在 GDPR 中被称为“数据主体”）提供权限，以管理由雇主或其他类型机构或组织（称为“数据控制者”或简称为“控制者”）收集的个人数据。 依据 GDPR，个人数据被广泛定义为与一个已识别的或可识别的自然人相关的任何数据。 GDPR 为数据主体提供其个人数据的特定权限；这些权限包括获取数据副本、请求修改数据、限制数据处理、删除数据，或者以电子表格形式接收数据，以便此数据可以转移给另一个控制者。 数据主体向控制者发出的在其个人数据上执行操作的正式请求称为“数据主体权限 (DSR) 请求”。

本文讨论了如何使用 Microsoft 的产品、服务和管理工具来帮助控制者在响应 DSR 时发现和处理个人数据。 具体而言，本文包括如何查找、访问和处理驻留在 Microsoft 云中的个人数据。 以下是本指南中所述的过程的快速概览：

1. 发现：使用搜索和发现工具以更轻松地查找可能是 DSR 主体的客户数据。 一旦收集潜在的响应式文档，便可执行以下步骤中所述的一个或多个 DSR 操作来响应请求。 或者，可以确定请求不符合组织有关响应 DSR 的指导准则。 [Microsoft Flow DSR 发现文档](gdpr-dsr-discovery.md)

1. 访问：检索驻留在 Microsoft 云中的个人数据，如果收到请求，则复制一份可供数据主体使用的副本。

1. 纠正：在适用情况下，对个人数据进行更改或执行其他请求的操作。

    如果数据主体要求纠正驻留在组织中的个人数据，你和你的组织必须确定是否接受此请求。  纠正数据可能包括采取诸如编辑、编校或删除个人数据等操作。

    Azure Active Directory 可用于管理 Microsoft Flow 用户的身份标识。 企业客户可以根据给定的 Microsoft 服务的性质来管理 DSR 纠正请求，包括有限的编辑功能。  作为数据处理方，Microsoft 不提供纠正系统生成的日志的功能，因为这些日志反映真实的活动，并构成 Microsoft 服务内部事件的历史记录。  [了解 DSR 的详细信息](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure)。

1. 限制：限制对个人数据的处理，可以通过取消各种在线服务的许可证，或者在可能的情况下关闭所需的服务。 此外还可以从 Microsoft 云中删除数据，并将其保留在本地或另一个位置。

    数据主体可能会请求你限制对其个人数据的处理。  Microsoft 为此目的提供了应用程序编程接口 (API) 和用户界面 (UI)。  这些接口允许企业客户的租户管理员通过数据导出和数据删除组合来管理这些 DSR。 客户可以 (1) 导出用户个人数据的电子副本，包括帐户、系统生成的日志和关联日志，然后 (2) 删除驻留在 Microsoft 系统中的帐户和关联数据。

1. 删除：永久删除驻留在 Microsoft 云中的个人数据。 [了解有关删除个人数据的详细信息](gdpr-dsr-delete.md)。

1. 导出：向数据主体提供个人数据的电子副本（采用计算机可读格式）。 本指南中的每一节都概述了数据控制者组织可以采取的技术步骤，以响应针对 Microsoft 云中个人数据的 DSR。 [了解有关导出个人数据的详细信息](gdpr-dsr-export.md)。

## <a name="system-generated-logs"></a>系统生成的日志

有关 Microsoft Flow 系统生成日志的详细信息，请参阅本[指南](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)。
