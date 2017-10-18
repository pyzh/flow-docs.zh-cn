---
title: "Microsoft Flow 的区域概述 | Microsoft Docs"
description: "有关 Microsoft Flow 中区域的问题与解答概述"
services: 
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
ms.openlocfilehash: ec9b72e570c562c091aefd370f73d6862ff56f18
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="faq-for-regions-in-microsoft-flow"></a>有关 Microsoft Flow 中的区域的常见问题
本文档提供有关 Microsoft Flow 的常见问题列表。

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>如何查明流部署在哪里？
流部署在托管[环境](environments-overview-admin.md)的[区域](https://azure.microsoft.com/regions/)中。 例如，如果环境是在欧洲区域创建的，则流部署在欧洲数据中心。

如果管理员登录到 Microsoft Flow [管理中心](https://admin.flow.microsoft.com)，那么他们可以识别该区域。 “环境”选项卡列出所有现有环境及其区域。

![查看环境](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>可以使用哪些区域？
* 美国
* 欧洲
* 亚洲
* 澳大利亚
* 印度
* 日本
* 加拿大

## <a name="what-features-are-specific-to-a-given-region"></a>哪些功能特定于某个给定区域？
可以在不同区域创建环境并将其绑定到该地理位置。 在环境中创建流时，此流会部署到该地理位置的数据中心。 这适用于在该环境中创建的任何项目，包括通用数据模型、流、连接、网关、应用和自定义连接器。

为了优化性能，请在最靠近用户的区域创建环境。 例如，如果用户位于欧洲，则在欧洲区域创建环境。 如果用户位于美国，则在美国区域创建环境。

## <a name="gateways"></a>网关
网关具有以下特点：

* 不可用于印度区域。
* 仅在默认环境中受支持，不在自定义环境中受支持。

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Microsoft Flow 在国家/地区云中是否可用？
Microsoft Flow 在国家/地区云中不可用。 我们已计划在 2018 年支持国家/地区云。

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>每个区域使用什么出站 IP 地址？
请参阅[限制和配置](limits-and-config.md)。

