---
title: "开始生成 | Microsoft Docs"
description: "创建自定义连接器，执行共享、嵌入流等操作。"
services: 
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: barathb
ms.openlocfilehash: d22193ac40b6eb8f90abf2ae5ced91b39c2faad9
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="start-to-build-with-microsoft-flow"></a>开始使用 Microsoft Flow 进行生成
使用 Microsoft Flow 通过以下方式以及其他方式扩展应用程序：

* 创建自定义连接器并进行连接
* 将该 API 与 Microsoft Flow 的所有用户共享
* 从应用内嵌入流体验
* 利用所有开发人员 API，使用户能够以最适合自己的方式与 Microsoft Flow 交互

## <a name="prerequisites"></a>先决条件
* 在 [flow.microsoft.com](https://flow.microsoft.com) 上有一个帐户

## <a name="create-a-custom-connector"></a>创建自定义连接器
如果需要通过 Microsoft Flow 实现所拥有的 Web 服务的自动化操作，首先需生成自定义连接器。 注册自定义连接器相当于将 Web API 的特征告知 Microsoft Flow，这些特征包括：所需身份验证、所支持的触发器和操作，以及每项此类操作的参数和输出。

按[此教程](https://powerapps.microsoft.com/tutorials/register-custom-api/)的说明注册自定义连接器。 注册后即可在组织内共享，让其他人帮忙测试。

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>与所有 Microsoft Flow 用户共享自定义连接器
对自定义连接器进行完整的测试以后，请按[此博客文章](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/)中的说明开始审核过程：

* 一个 OpenAPI 文件，代表 API 以及任何身份验证信息
* 连接器的图标
* API 的说明
* 大约 10 项建议，说明其他用户如何通过模板使用 API

在提交此信息后，Microsoft 就会开始在 Microsoft Flow 和 Microsoft PowerApps 中评估用户 API 的功能。

## <a name="embed-the-flow-experience-in-your-website-or-app"></a>在网站或应用中嵌入流体验
最后，可以在应用内嵌入 Microsoft Flow，在应用和 Microsoft Flow 支持的所有其他服务之间进行深入的上下文集成。 例如，可以执行以下操作：

* 浏览与服务相关的所有模板，让用户选择一个模板
* 管理用户的与应用相关的流

请参阅[此教程](embed-flow-dev.md)，详细了解如何在应用内嵌入 Microsoft Flow。

