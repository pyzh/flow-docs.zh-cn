---
title: Microsoft Flow GDPR 数据主体请求发现 | Microsoft Docs
description: 了解如何使用 Microsoft Flow 来响应 GPDR 数据主体发现请求。
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
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 9f950da1b62eac66b35a667f307917f704eb9133
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>响应 Microsoft Flow 的 GDPR 数据主体发现请求

响应 DSR 的第一步是查找请求主体的个人数据。 此第一个步骤可帮助你确定 DSR 是否符合组织要求以接受或拒绝 DSR 请求。 例如，在发现和审查相关个人数据之后，你可能会确定该请求不符合组织要求，因为这样做可能会对他人的权利和自由产生负面影响。

下面是包含特定用户个人数据的 Microsoft Flow 资源类型的摘要。

|包含个人数据的资源|用途|
|-----|-----|
|系统生成的日志|捕获系统事件和历史记录的遥测。|
|运行历史记录|过去 28 天内每个流执行的历史记录。 此数据包括流的开始时间、结束时间、状态和所有输入/输出信息。 [了解详情](https://flow.microsoft.com/blog/download-history-recurrence/)|
|活动源| 提供流活动的概述，包括运行状态、故障和通知。|
|用户作业|不向用户显示，为了让流执行而代表用户运行的系统作业。|
|流|为流而存在的工作流逻辑。 [了解详情](https://docs.microsoft.com/flow/get-started-logic-flow)|
|流权限|流可以共享和重新分配给其他用户。 所有流都有权限列表。 [了解详情](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|用户详细信息|支持流执行的详细信息，用户不可见。|
|连接|由连接器使用，并允许连接到 API、系统、数据库等。 [了解详情](https://docs.microsoft.com/flow/add-manage-connections)|
|连接权限|特定连接的权限。 [了解详情](https://docs.microsoft.com/flow/add-manage-connections)|
|自定义连接器|由用户创建和发布的自定义连接器允许连接到自定义或第三方系统。 [了解详情](https://docs.microsoft.com/connectors/custom-connectors/)|
|自定义连接器权限|自定义连接器的权限列表。 [了解详情](https://docs.microsoft.com/connectors/custom-connectors/share)|
|网关|网关是可以由用户安装的本地数据服务，可以在 Microsoft Flow 和非云数据源之间快速安全地传输数据。 [了解详情](https://docs.microsoft.com/flow/gateway-manage)|
|网关权限|网关可以与组织中的用户共享。 [了解详情](https://go.microsoft.com/fwlink/?linkid=872249)|
