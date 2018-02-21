---
title: Common Data Service | Microsoft Docs
description: "创建一个流，以通过通用数据服务导入数据、导出数据或生成审批。"
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: e4e92bfdcf1ea65de272233b2056523641010cf2
ms.sourcegitcommit: f3261717768177e03e825c0dd2e3ba736dc9b94d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>创建使用通用数据服务的流
创建使用[通用数据服务](https://powerapps.microsoft.com/tutorials/data-platform-intro/)的流，通过统一的视图查看业务数据，提高运营效率。 将这个安全的业务数据库部署到组织中，该数据库包含各种格式正确的标准业务实体（例如“销售”、“购买”、“客户服务”和“工作效率”）。 将组织数据存储在一个或多个[自定义实体](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/)中，后者相对于外部数据源（例如 Microsoft Excel 和 Salesforce）具有多项优势。

例如，可以在 Microsoft Flow 中以下述主要方式充分利用通用数据服务：

* 创建一个流，以便导入数据、导出数据或根据数据执行操作（例如发送通知）。 请注意，此方法并非完全同步服务，只是让用户按实体移进或移出数据。
  
    有关详细步骤，请参阅本主题后面的过程。
* 不必[通过电子邮件创建审批循环](wait-for-approvals.md)，只需创建一个流，将审批状态存储在实体中，同时生成一个自定义应用，允许用户在其中批准或拒绝项目即可。
  
    有关详细步骤，请参阅[使用通用数据服务生成审批循环](common-data-model-approve.md)。

**先决条件**

* 注册到 [Microsoft Flow](https://flow.microsoft.com) 和 [PowerApps](https://web.powerapps.com)。
  
    如果出现问题，请确保 [Microsoft Flow](sign-up-sign-in.md) 和 [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) 支持所用的帐户类型，且组织没有禁用注册。
* 如果从未用过通用数据服务，请打开 [powerapps.com](https://web.powerapps.com/#/entities) 的“实体”选项卡，然后单击或点击“创建数据库”。

## <a name="sign-in-to-your-environment"></a>登录环境
1. 打开 [Microsoft Flow 门户](https://flow.microsoft.com)，然后单击或点击右上角的“登录”。
   
    **注意**：可能需要打开左上角菜单才能显示“登录”按钮。
   
    ![登录](./media/common-data-model-intro/signin-flow.png)
2. 在右上角菜单中，选择用户在 powerapps.com 中创建数据库的环境。
   
    **注意**：如果未选择相同的环境，则将看不到用户的实体。
   
    ![选择环境](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>打开模板
1. 在屏幕顶部的“搜索模板”框中，键入或粘贴“通用”，然后按 Enter。
   
    ![搜索模板](./media/common-data-model-intro/template-search.png)
2. 在模板列表中，单击或点击模板，将数据从所需源导入所需实体（或对象）。
   
    例如，单击或点击模板，将联系人信息从 Dynamics 365 复制到通用数据服务中。
   
    ![选择模板](./media/common-data-model-intro/choose-template.png)
3. 单击或点击“使用此模板”。
   
    ![使用模板](./media/common-data-model-intro/use-template.png)
4. 如果尚未创建从 Microsoft Flow 到 Dynamics 365 的连接，可单击或点击“登录”，然后在系统提示时提供凭据。
   
    ![登录 Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. 单击或点击“继续”。
   
    ![确认帐户](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>生成流
1. 在第一张卡片中，指定会触发流的事件。
   
    例如，用户需要生成一个流，将新的联系人从 Dynamics 365 的实例复制到通用数据服务中。 在“创建记录时”下指定实例，方法是：单击或点击向下箭头，然后单击或点击所显示列表中的选项。
   
    ![指定 Dynamics 365 的实例](./media/common-data-model-intro/specify-instance.png)
2. （可选）在屏幕顶部附近，为要创建的流指定其他名称。
   
    **注意**：如果浏览器窗口没有最大化，UI 看起来可能会稍有不同。
   
    ![命名流](./media/common-data-model-intro/name-flow.png)
3. 单击或点击“创建流”。
   
    **注意**：如果浏览器窗口没有最大化，可能仅显示复选标记。
   
    ![创建流](./media/common-data-model-intro/create-flow.png)

现在，在源系统中创建该对象后，系统就会将其导入通用数据服务中。 如果找不到所需模板，则可[从头开始生成流](get-started-logic-flow.md)，让其基于通用数据服务运行。

用户可以在数据库发生更改时执行相关操作。 例如，可以在数据更改时发送通知邮件。

