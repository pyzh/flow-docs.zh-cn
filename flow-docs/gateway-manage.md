---
title: 了解如何管理本地数据网关 | Microsoft Docs
description: 在 Microsoft Flow 中查看和安装本地数据网关
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/05/2018
ms.author: deonhe
ms.openlocfilehash: 642cf26110a09404c8bd453f894540963904ebda
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "29057398"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>在 Microsoft Flow 中管理本地数据网关

通过 Microsoft Flow 安装和管理本地数据网关，将各种基于云的应用与本地数据和应用安全地进行集成。

使用网关可以通过以下这些连接连接到本地数据：

* SharePoint
* SQL Server
* Oracle
* Informix
* Filesystem
* DB2

> [!IMPORTANT]
> Microsoft SharePoint 数据网关现在支持 HTTP 和 HTTPS 流量。


## <a name="prerequisites"></a>先决条件

* 用户名和密码，[注册](sign-up-sign-in.md)到 Microsoft Flow 时使用过。
* 网关的管理权限。

  默认情况下，你拥有安装的每个网关的这些权限。 此外，另一个网关的管理员可以向你授予该网关的这些权限。
* 支持网关的许可证。 有关详细信息，请参阅[定价页](https://flow.microsoft.com/pricing/)的“连接”部分。

> [!NOTE]
> 只能在你的[默认环境](environments-overview-maker.md)中创建网关和本地连接。



## <a name="view-your-gateways"></a>查看网关

在 [Microsoft Flow 网站](https://flow.microsoft.com)的右上角，选择齿轮图标，然后选择“网关”。

![托管网关][1]

> [!NOTE]
> 如果在 PowerApps 中创建了网关或被授予对网关的访问权限，该网关将出现在 Microsoft Flow 的“我的网关”中。



## <a name="install-a-gateway"></a>安装网关

1. 下载[“网关安装向导”](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)。

1. 运行此向导，并提供用于登录到 Microsoft Flow 的相同凭据。

    成功注册和配置网关后，网关就会显示在 Microsoft Flow 的“网关”列表中。

有关详细信息，请参阅[了解网关](gateway-reference.md)。

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
