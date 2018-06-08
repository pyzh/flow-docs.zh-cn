---
title: 适用于企业开发人员、ISV 和合作伙伴的 Microsoft Flow | Microsoft Docs
description: 开发 Microsoft Flow 解决方案简介。
services: ''
suite: flow
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: mblythe
ms.openlocfilehash: d8886f0828ca3b8ccf7ae1ce9c46f6e9b8fcc766
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "29351277"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>适用于企业开发人员、ISV 和合作伙伴的 Microsoft Flow

作为开发人员，你可以扩展 Microsoft Flow，为组织和客户提供更强大的解决方案。

## <a name="microsoft-flow-for-enterprise-developers"></a>适用于企业开发人员的 Microsoft Flow

作为企业开发人员，你的目标是让组织能够在 Microsoft Flow 上生成功能强大的定制解决方案：

- 生成自定义连接器：开发自定义连接器，以便通过 Microsoft Flow 连接到组织的数据和 Web 服务。 [了解详情](https://docs.microsoft.com/connectors/custom-connectors/)

- 生成 Azure Functions：创建 Azure Functions，以便通过自定义的服务器端逻辑来扩展应用。 [了解详情](https://docs.microsoft.com/azure/azure-functions/functions-flow-scenario)

- 嵌入 Microsoft Flow：将 Microsoft Flow 直接嵌入网站体验中，以便创建集成式解决方案，呈现组织中已完成自己工作的人员的工作流或过程。 [了解详情](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>适用于 ISV 和 Microsoft 合作伙伴的 Microsoft Flow

作为 Microsoft 合作伙伴或独立软件供应商 (ISV)，通过扩展你的产品以与客户的数据和业务流程集成，加速客户采用，并添加和自定义工作流以在应用程序中自动执行业务流程。 完成以下七个步骤后，应用程序可利用可靠的云规模工作流引擎，连接 200 多种不同的服务。

| 阶段 | 步骤 | 适用场景 |
| --- | --- | --- |
| 开发 | 1.为数据生成自定义连接器 | 希望向 PowerApps 或 Microsoft Flow 公开自己的 ISV 数据时 |
| 开发 | 2.添加对应用程序的支持，使用 Azure Active Directory (Azure AD) 对用户进行身份验证 | 希望在 Microsoft AppSource 中嵌入 Microsoft Flow UI 或列表时 | 
| 开发 | 3.使用基于 Web 的 iframe 将 Microsoft Flow UI 嵌入应用程序 | 希望在应用程序中包含流创建或流管理时 | 
| 开发 | 4.创建并发布流模板 | 希望为客户预生成流时 | 
| 开发 | 5.添加应用程序逻辑，以编程方式部署流 | 希望为客户自动部署预生成流时 | 
| 分发 | 6.通过 Microsoft 云解决方案提供商计划向客户授予 Microsoft Flow 许可 | 客户没有 Office 365 或 Dynamics 365 许可证时 |
| 分发 | 7.在 Microsoft AppSource 上列出解决方案 | 建议用于提高 ISV 解决方案的可见性 |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1.连接到 API 或允许客户连接到 API

通常，ISV 拥有专有数据且希望客户通过其流访问这些数据。 通过自定义连接器即可公开任何数据的访问权限。 [了解详情](https://docs.microsoft.com/connectors/custom-connectors/)

创建连接器后，可通过两种方式向客户提供连接器：
- 可通过 REST API 或 PowerShell 将连接器部署到客户的租户中。
- 若要面向所有用户公开发布自定义连接器，可提交连接器进行认证。 [了解详情](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2.身份验证 

若要调用 REST API 并嵌入已通过身份验证的 UI，应用程序需使用 Azure AD 联合单一登录对最终用户和客户进行身份验证。 [转到此处](https://identity.microsoft.com/)，了解如何启用 AAD 联合 SSO。 我们不支持未经身份验证的访问，也不支持通过 Azure AD 以外的标识提供者进行访问。 

### <a name="3-embedding-ui-components"></a>3.嵌入 UI 组件

在应用内嵌入 Microsoft Flow，以便在应用和 Microsoft Flow 支持的所有其他服务之间进行深入的上下文集成。 [了解详情](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4.创建并发布流模板

有了连接器以后，应发布模板来演示如何使用你的服务。 这些模板将充当示例，可供用户学习并扩展其自己的独特工作流。 [了解详情](publish-a-template.md)

### <a name="5-deployment"></a>5.部署

若要让最终用户可访问他们能自动使用的流，可将这些流部署到用户的 Azure AD 租户中。 使用通过 REST API 或 PowerShell 部署的部署包。 [了解详情](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6.授权

如果客户已经拥有 Office 365 或 Dynamics 365，且这些许可证与用户登录 Azure AD 的标识相关联，则无需另外授权。 但是，如果客户未使用 Office 365 或 Dynamics 365，那么你应代表他们获取 Microsoft Flow 的使用权，这样他们才能获得许可，从而在应用程序中利用这些嵌入的组件。

我们提供 [Microsoft 云解决方案提供商](https://partner.microsoft.com/cloud-solution-provider)计划，可代表客户获得许可证。 Microsoft Flow 提供两种[定价计划](https://flow.microsoft.com/pricing/)，请查看计划和功能详细信息。

### <a name="7-list-on-appsource"></a>7.在 AppSource 上列出

将 Microsoft Flow 集成到应用程序中后，即可在 AppSource 上将其列出。 通过 AppSource 可生成应用并将其发布到 AppSource 供新客户试用，从而为自己的企业带来新的潜在客户。 [了解详情](dev-appsource-test-drive.md)
