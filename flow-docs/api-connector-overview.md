---
title: "API 连接器概述 | Microsoft Docs"
description: "ISV 和 SaaS 服务所有者可以生成连接器并获得 Microsoft 的认证。"
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 62f8f8d0af72292a61324d75bd46f53d559b46a3
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-overview-microsoft-flow"></a>API 连接器概述 (Microsoft Flow)
**API 连接器**是一个基于 OpenAPI (Swagger) 且围绕 REST API 的包装器，可供基础服务与 [Microsoft Flow](https://flow.microsoft.com)、[PowerApps](https://powerapps.microsoft.com) 和[逻辑应用](https://docs.microsoft.com/azure/logic-apps/)通信。 用户可以通过它来连接其帐户，并充分利用一组预建的**触发器**和**操作**来生成其应用和工作流。

作为**独立软件供应商 (ISV)** 或 **SaaS 服务所有者**，你可以通过生成连接器为用户启用各种业务和生产效率方案。 有了连接器，你将不再局限于固定的一组集成，从而提高服务的可达性、可发现性和使用效率。

## <a name="requirements"></a>要求
若要生成和提交连接器，你的服务必须满足以下要求：

* 商业用户方案适合 Microsoft Flow、PowerApps 和逻辑应用
* 服务已公开发布且具有稳定的 REST API

## <a name="build-your-connector"></a>生成连接器
若要生成 API 连接器，第一步是生成功能完全正常的自定义连接器。 自定义连接器具有与 API 连接器完全相同的运行方式，但仅供其作者以及该作者的租户中的特定用户使用。

生成连接器的过程涉及多个步骤：

![API 连接器创作步骤](./media/api-connectors-overview/authoring-steps.png)

[详细了解](api-connector-dev.md)如何开发 API 连接器。

## <a name="submit-for-certification"></a>提交后即可认证
生成连接器后，即可提交该连接器进行认证。 Microsoft 会按照第三方认证过程，在发布连接器之前对其进行审核。

该过程会在 Microsoft Flow 和 PowerApps 中对连接器的功能进行验证，并从技术和内容角度检查其符合性。

[详细了解](api-connector-submission.md)提交连接器进行认证和发布的过程。

## <a name="get-support"></a>获取支持
如需载入和开发支持，请发送电子邮件至 [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com)。此帐户会受到积极监视和管理。 开发人员查询和事件将会快速转交给相应的团队进行处理。

