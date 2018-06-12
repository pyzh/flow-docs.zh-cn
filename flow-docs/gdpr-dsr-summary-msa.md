---
title: Microsoft 帐户 (MSA) 的 GDPR 数据主体请求摘要 | Microsoft Docs
description: 了解如何响应 Microsoft Flow 的 GPDR 数据主体请求。
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
ms.date: 5/16/2018
ms.author: keweare
ms.openlocfilehash: b6fdcd33fd657086a5d37919858eceefabd18934
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34562942"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>响应 GDPR 数据主体权限 (DSR) 请求

本文介绍欧盟的一般数据保护条例 (GDPR)，并提供可用于支持通过 Microsoft 帐户 (MSA) 进行身份验证的 Microsoft Flow 用户的 GDPR 符合性的步骤。

## <a name="prerequisites"></a>先决条件

需要具有[自由 Microsoft Flow 许可证](https://flow.microsoft.com/pricing/)的 MSA 才能执行本文中的步骤。

>[!TIP]
> 通过 [Azure Active Directory 帐户](gdpr-dsr-summary.md)进行身份验证的用户也可使用 GDPR 符合性信息。
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>响应 Microsoft Flow 客户数据的 DSR

数据主体向控制者发出的在其个人数据上执行操作的正式请求称为“数据主体权限 (DSR) 请求”。 GDPR 将个人数据定义为“与已识别的或可识别的自然人相关的任何数据”。 GDPR 为用户（称为数据主体）提供管理由雇主、机构或组织（称为数据控制者或控制者）收集的个人数据的权限。 这些权限包括：

* 获取个人数据的副本。
* 请求对个人数据进行更正。
* 限制对个人数据的处理。
* 删除个人数据。
* 以电子格式接收个人数据，便于移动到另一控制者。

Microsoft 提供了产品、服务和工具来帮助控制者在响应云中的数据的 DSR 请求时发现和处理个人数据。

以下是本指南中所述过程的概览：

1. **发现**：使用搜索和发现工具轻松查找可能是 DSR 请求主体的客户数据。 如果确定所收集的文档符合采取操作的控制者准则，则可执行以下步骤中所述的一个或多个 DSR 操作。 请参阅 [Microsoft 帐户的 Microsoft Flow DSR 发现文档](gdpr-dsr-discovery-msa.md)，了解详细信息。 或者，可以确定请求不符合响应 DSR 请求的控制者准则。

1. **访问**：检索驻留在 Microsoft 云中的个人数据，如果收到请求，则复制一份可供数据主体使用的副本。

1. **纠正**：在适用情况下，对个人数据进行更改或执行其他请求的操作。

1. **限制**：限制对个人数据的处理，可以通过取消各种联机服务的许可证，或者在可能的情况下关闭所需的服务。 此外还可以从 Microsoft 云中删除数据，并将其保留在本地或另一个位置。

1. **删除**：永久删除驻留在 Microsoft 云中的个人数据。 详细了解如何[删除 Microsoft 帐户的个人数据](gdpr-dsr-delete-msa.md)。 详细了解如何[关闭 Microsoft 帐户](gdpr-dsr-accountclose-msa.md)。

1. **导出**：提供个人数据的电子副本（采用计算机可读格式）。 [详细了解如何导出 Microsoft 帐户的个人数据](gdpr-dsr-export-msa.md)。