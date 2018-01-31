---
title: "提交以认证为 API 连接器 | Microsoft Docs"
description: "连接器在获得认证后即可供 Microsoft Flow、PowerApps 和逻辑应用的所有用户使用。"
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
ms.openlocfilehash: 33283e1f682190f6aea02cb61a31cb43b42d5289
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="submit-your-connectors-for-microsoft-certification"></a>提交连接器以供 Microsoft 进行认证
若要向 Microsoft Flow、Azure 逻辑应用和 Microsoft PowerApps 中的所有用户公开发布自定义连接器，请向 Microsoft 提交连接器以供 Microsoft 进行评审、验证和发布审批。 

## <a name="certification-criteria"></a>认证条件
| 功能 | 详细信息 | 必需或建议 |
| --- | --- | --- |
| 软件即服务 (SaaS) 应用 |满足能够良好适应逻辑应用、Flow 和 PowerApps 的用户方案。 |必需 |
| 身份验证类型 |API 必须支持 OAuth2、API Key 或基本身份验证。 |必需 |
| 支持 |必须提供一位负责支持的联系人，以便客户获取帮助。 |必需 |
| 可用性和运行时间 |应用必须至少在 99.9% 的时间内正常运行。 |建议 |
|  | | |

此外，如果非 Microsoft 合作伙伴或独立软件供应商 (ISV) 想要认证并公开发布连接器，则必须拥有基础服务或展示使用 API 的明确权限。

若要获得认证，连接器必须接受两个阶段的评审： 

1. 功能验证
   
    自定义连接器必须接受以下方面的评估：
   
   * 自定义连接器向导中的“定义”部分中的无效 Swagger 或 JSON 错误
   * 向导的测试部分中的运行时和架构验证错误
     
     因此，每个操作都将在 Flow、逻辑应用和 PowerApps 中经过全面测试，以查看是否存在任何客户端错误。
2. 内容验证
   
    精心编写的连接器会为每个实体使用友好名称并提供说明。 我们将评估 Swagger，以确保每个操作、输入参数和响应属性都包含：
   
   * [摘要](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#summary)
   * [说明](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#description)
   * [可见性信息](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#visibility)

## <a name="nominate-and-submit-your-connector-to-microsoft-for-certification"></a>向 Microsoft 提名并提交连接器以进行认证
若要申请认证，请遵循下列步骤：

1. **提名**
   
   1. [提交提名](https://go.microsoft.com/fwlink/?linkid=848754)。
   2. 签署所收到的相互保密协议和合作伙伴协议。 
      在继续下一步之前，Microsoft 要求签署这些合同。 
      然后，我们才可以检查连接器是否满足认证条件。 
   3. 如果连接器获得批准，Microsoft 将发送通知，并附带有关上架的说明。
2. **审核**
   
   1. 向提名联系人发送以下信息以供评审：
      
      * 描述 API 的 OpenAPI 文件
      * 表示连接器的图标文件（.png 或 .jpg）。 （图标应在约 230 像素的方形内具有约 160 像素的徽标。 首选使用彩色背景的白色徽标。）
      * 采用十六进制格式的图标品牌颜色，该颜色应与图标文件中的彩色背景匹配
      * 用于验证的测试帐户
      * 负责支持的联系人
   2. 如果我们需要更多信息，我们将与你联系。
3. **发布**
   
    验证连接器的功能和内容后，我们会着手将连接器部署到所有产品和区域。 通常，认证和部署过程最长需要 3 周。
   
    默认情况下，所有连接器在发布时均为“高级”。 
    如果应用使用 Azure 生成，则可以申请将连接器作为“标准”连接器上架，以供 Office 365 企业版计划的所有用户使用。 
    有关更多详细信息，请询问提名联系人。

