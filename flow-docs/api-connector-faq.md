---
title: "API 连接器常见问题解答 | Microsoft Docs"
description: "查找与要求、触发器以及其他领域有关的问题的答案。"
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
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 1715700fa6a94bb35733865556a2c9be0ba3ce9f
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-faq-microsoft-flow"></a>API 连接器常见问题 (Microsoft Flow)
## <a name="requirements"></a>要求
**问：**能否在不使用 REST API 的情况下生成连接器？ </br>
答：否，若要生成连接器，必须通过支持手段为服务提供稳定的 HTTP REST API。 

**问：**可以使用哪些工具生成连接器？ </br>
答：Azure 具有可用于将任何服务公开为 API 的功能和服务，例如用于托管的 Azure App Service、API 管理等。

**问：**支持哪些身份验证类型？ </br>
答：可以使用以下受支持的身份验证标准：

* [OAuth 2.0](https://oauth.net/2/)，包括 [Azure Active Directory](https://azure.microsoft.com/develop/identity/)，或特定的服务，例如 Dropbox、GitHub 和 SalesForce
* 通用 OAuth 2.0
* [基本身份验证](https://swagger.io/docs/specification/authentication/basic-authentication/)
* [API 密钥](https://swagger.io/docs/specification/authentication/api-keys/)

## <a name="triggers"></a>触发器
**问：**能否在没有 Webhook 的情况下生成触发器？ </br>
答：否，适用于 Azure 逻辑应用和 Microsoft Flow 的自定义连接器仅支持基于 Webhook 的触发器。 如果要请求其他实现模式，请联系 [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com)，告知有关 API 的更多详细信息。

## <a name="certification"></a>认证
**问**：我不是 Microsoft 合作伙伴或独立软件供应商 (ISV)。 我是否仍然可以创建连接器？ </br>
答：是，可以注册这些连接器以供在组织内部使用，但如果要认证并公开发布连接器，则必须拥有基础服务或展示使用 API 的明确权限。

## <a name="other"></a>其他
**问：**我的 API 使用动态主机。 如何使用 OpenAPI 实现它们？ </br>
答：自定义连接器不支持动态主机。 请改用静态主机进行开发和测试。 如果想要认证连接器，请询问 Microsoft 联系人有关动态实现的信息。

**问：**是否支持 Postman Collection V2？ </br>
答：否，当前仅支持 Postman Collection V1。

**问：**是否支持 OpenAPI 3.0？ </br>
答：否，当前仅支持 OpenAPI 2.0。

