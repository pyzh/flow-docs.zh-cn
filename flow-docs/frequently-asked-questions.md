---
title: 常见问题 | Microsoft Docs
description: 有关 Microsoft Flow 的几个常见问题的解答
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
ms.date: 03/15/2017
ms.author: stepsic
ms.openlocfilehash: 4fa6af7557fdbae46db5eb74a82a9d30a991e93b
ms.sourcegitcommit: f0202f74ba9a2282a670a1751462f598a5ea0ce5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="frequently-asked-questions"></a>常见问题
## <a name="audience-and-strategy"></a>受众和策略
### <a name="what-is-microsoft-flow"></a>Microsoft Flow 是什么？
Microsoft Flow 是一种基于云的简单且实用的服务，适合业务线用户生成工作流，以便自动完成各种耗时且跨应用程序和服务的业务任务和过程。

### <a name="who-is-the-intended-audience-for-microsoft-flow"></a>Microsoft Flow 的目标受众是谁？
Microsoft Flow 有两类不同的受众：

* 企业型组织中的业务线“普通集成商”，他们需与 IT 部门合作，使业务解决方案更切合业务本身。
* IT 决策者，他们需为创建自己的解决方案的业务线合作伙伴提供支持，让 IT 专业人员和集成专家能够将精力集中于更高级的集成工具（例如 Azure 逻辑应用）。

### <a name="how-do-microsoft-flow-and-logic-apps-relate-to-each-other"></a>Microsoft Flow 和逻辑应用彼此的关系如何？
Microsoft Flow 提供的功能适合业务线用户创建自动化工作流。 逻辑应用是一种 Azure 服务，可提供与 Microsoft Flow 一样的强大功能，也可提供其他功能，例如集成 Azure 资源管理器和 Azure 门户、PowerShell 和 xPlat CLI、Visual Studio 以及其他连接器。 [详细了解逻辑应用](https://azure.microsoft.com/services/app-service/logic/)。

### <a name="how-does-microsoft-flow-fit-in-microsofts-overall-business-application-platform-strategy"></a>Microsoft Flow 在 Microsoft 的总体业务应用程序平台策略中的地位如何？
Microsoft Flow 是该商业应用程序平台的一部分，该平台功能强大且适应性强，其中包括 PowerApps、Common Data Service、Dynamics 365 和 Office 365。 该平台可以方便客户、合作伙伴、ISV 合作伙伴创建适合自己公司、行业、职能角色甚至特定地理位置的专用解决方案。 业务线用户对自己的业务需求了解最深，因此可以轻松地分析、组合和优化数据和流程。 专业开发人员可以轻松地对自动化、分析和业务线应用进行扩展，充分利用函数、应用服务和逻辑应用之类的 Azure 服务。 API 连接器、网关和 Microsoft Common Data Service 方便用户充分利用已经在云中或本地使用的服务或数据。

## <a name="functionality"></a>功能
### <a name="what-do-i-need-to-use-microsoft-flow"></a>使用 Microsoft Flow 有哪些要求？
只需一个 Web 浏览器和一个电子邮件地址即可使用 Microsoft Flow。

### <a name="what-browsers-does-microsoft-flow-support"></a>Microsoft Flow 支持哪些浏览器？
Microsoft Flow 支持 Microsoft Edge 以及最新版的 Chrome 和 Safari。

### <a name="which-email-addresses-are-supported"></a>支持哪些电子邮件地址？
Microsoft Flow 支持不以 .gov 和 .mil 结尾的电子邮件地址。  

### <a name="is-microsoft-flow-available-on-premises"></a>Microsoft Flow 是否可在本地使用？
Microsoft Flow 是只能公用的云服务。 但是，用户可以通过本地数据网关安全地连接到自己的本地服务。

### <a name="what-services-can-microsoft-flow-connect-to"></a>Microsoft Flow 可以连接到什么服务？
Microsoft Flow 可以连接到 100 多个现成的数据源，这些数据源的数目仍在增加。 数据源和服务的部分示例如下：

* SharePoint
* Dynamics 365
* OneDrive
* OneDrive for Business
* Google Drive
* Google Sheets
* Trello
* Twitter
* Box
* Facebook
* SalesForce.com
* Mailchimp
* 自定义 API

如需可用连接器的完整列表，可单击[此处](https://go.microsoft.com/fwlink/?LinkId=832211)。

可以通过[本地数据网关](gateway-manage.md)访问用户自己的 IT 基础架构中的数据源。

### <a name="what-are-templates"></a>模板是什么？
模板是预生成的流，适合流行的和常见的方案。 使用模板时，只需获得模板中服务的访问权限并填写所需设置即可。

### <a name="what-data-sources-will-i-be-able-to-connect-to"></a>可以连接到哪些数据源？
可以连接到 Microsoft 和第三方提供的 100 多种标准服务，例如 Office 365、Twitter、SharePoint、OneDrive、Dropbox、SQL Server 等。 用户还可以连接到高级服务，如 Salesforce 和 PowerApps 的通用数据服务。

### <a name="how-do-i-connect-to-a-rest-api-in-my-flow"></a>如何在流中连接到 REST API？
你可以连接到任何 REST API，只要该 REST API 使用 JSON 并通过创建[自定义连接器](register-custom-api.md)支持 10 多种身份验证方法中的至少一种。

### <a name="how-do-i-connect-to-sql-server-and-other-on-premises-data-sources"></a>如何连接到 SQL Server 以及其他本地数据源？
可以使用[本地数据网关](gateway-manage.md)连接到本地网络中的服务。

### <a name="can-i-share-the-flows-i-create"></a>能否共享创建的流？
可以通过下述方法之一共享流：

* 可以将组织中的同事或组作为流的所有者来添加，使之也能编辑和管理流。
* 对于可以手动运行的流，也可向组织中的其他人员或组授予运行该流的相应权限。

### <a name="how-many-flows-can-i-have"></a>可以有多少个流？
Microsoft Flow 最多可以有 50 个流。 如需更多流，可提出相关请求。

### <a name="where-do-i-get-started-with-microsoft-flow"></a>学习 Microsoft Flow 该从何处着手？
可以从以下资源着手：

* [博客](https://flow.microsoft.com)
* [YouTube 频道](https://youtube.com/playlist?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF)
* [主题](getting-started.md)
* [社区](https://powerusers.microsoft.com)

### <a name="what-operating-systems-does-the-mobile-app-for-microsoft-flow-support"></a>适用于 Microsoft Flow 的移动应用支持哪些操作系统？
Microsoft Flow 移动应用可以在 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows) 上使用。

### <a name="can-flows-be-turned-off-or-disabled"></a>可以关闭流或者禁用流吗？

可以，每个流都有一个 on/off 开关，你可以从正在处理的请求中停止流。

请查看下表，理解流在重新打开时的响应方式。

触发器类型|说明
-------|--------
轮询，例如重复触发器|再次打开流时，会处理所有未处理/挂起的事件。
Webhook|再次打开流时，只处理在打开流以后生成的新事件。

### <a name="what-regions-and-languages-does-microsoft-flow-support"></a>Microsoft Flow 支持哪些区域和语言？
Microsoft Flow 支持 42 种语言，已在[六个区域](regions-overview.md)发布。

### <a name="how-does-microsoft-flow-compare-to-sharepoint-designer-2013"></a>Microsoft Flow 与 SharePoint Designer 2013 相比如何？
Microsoft Flow 是 SharePoint Designer 的接替版本，适合许多常见业务情况，如审批、文档审阅和入职/离职。 它是在 SharePoint 中生成先进的业务自动化方案的默认工具。

### <a name="how-does-microsoft-flow-ensure-that-corporate-data-isnt-accidentally-released-to-social-media-services"></a>Microsoft Flow 如何确保公司数据不会意外发布到社交媒体服务？
管理员可以创建[数据丢失防护策略](prevent-data-loss.md)，确保在 Microsoft Flow 中只使用认可的服务。

## <a name="licensing"></a>授权
### <a name="will-microsoft-flow-still-have-a-free-or-trial-option"></a>Microsoft Flow 是否仍有免费或试用版本？
是。 你可以使用用户权限受限的免费产品/服务，也可以注册 Microsoft Flow 的 90 天免费试用版。 在试用期间，用户可以随时激活订阅。

### <a name="what-pricing-plans-do-you-offer"></a>提供哪些定价计划？
Microsoft Flow 提供免费和付费服务级别。 [详细了解定价](billing-questions.md)。

## <a name="learn-more"></a>了解详情

* 开启 Microsoft Flow [引导学习之旅](guided-learning/index.yml)
* 通过[入门指南](getting-started.md)了解 Microsoft Flow 的基础知识