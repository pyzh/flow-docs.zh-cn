---
title: "数据丢失防护 (DLP) 策略简介。 | Microsoft Docs"
description: "Microsoft Flow 的数据丢失防护策略简介。"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/24/2016
ms.author: deonhe
ms.openlocfilehash: 29eaa9299e09c641538ab8f9dfbc9954bca66a3b
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="data-loss-prevention-dlp-policies"></a>数据丢失防护 (DLP) 策略
## <a name="what-is-a-data-loss-prevention-policy"></a>什么是数据丢失防护策略？
组织的数据是取得成功的关键所在。 组织的数据需要随时可用于决策，但必须受到保护，避免与无权访问这些数据的受众共享。 为了保护这些数据，Microsoft Flow (Flow) 提供了创建和实施策略的功能，用于定义可与哪些使用者服务/连接器共享特定的业务数据。 这些定义如何共享数据的策略称为数据丢失防护 (DLP) 策略。

## <a name="why-create-a-dlp-policy"></a>为何要创建 DLP 策略？
创建 DLP 策略能够明确定义可与哪些使用者服务共享业务数据。 例如，使用 Flow 的组织可能不希望其存储在 SharePoint 中的业务数据自动发布到其 Twitter 源。 为了防止出现这种情况，可以创建 DLP 策略，阻止将 SharePoint 数据用作推文来源。

## <a name="benefits-of-a-dlp-policy"></a>DLP 策略的优点
* 确保在整个组织中以统一的方式管理数据  
* 防止将重要业务数据意外发布到社交媒体站点等服务。   

## <a name="managing-dlp-policies"></a>管理 DLP 策略
**先决条件**  
若要创建、编辑或删除 DLP 策略，需要满足以下条件： 

* 拥有环境管理员或租户管理员权限。 可在[环境主题](environments-overview-admin.md)中了解有关权限的详细信息。  
* 有一个 [Flow P2 许可证](billing-questions.md)。  

## <a name="create-a-dlp-policy"></a>创建 DLP 策略
**先决条件**  
若要创建 DLP 策略，必须至少对一个环境拥有相应的权限。  

遵循以下步骤创建一个 DLP 策略，防止公司 SharePoint 中存储的数据发布到 Twitter：  

1. 在“数据策略”选项卡中，选择“新建策略”链接：  
   ![登录](./media/prevent-data-loss/create-policy-1.png)    
2. 在打开的页面顶部的“数据策略名称”标签中，输入“Contoso 的安全数据访问”作为 DLP 策略名称：   
   ![登录](./media/prevent-data-loss/create-policy-2.png)  
3. 在“[应用到](environments-overview-admin.md)”选项卡中选择“**环境**”。  
   **注意：**环境管理员可以创建仅应用到单个环境的策略。 租户管理员可以创建应用到所有环境、一个或多个选定环境或者除一组选定环境以外的所有环境的策略：  
   ![登录](./media/prevent-data-loss/create-policy-3.png)  
4. 选择“数据组”选项卡：  
   ![登录](./media/prevent-data-loss/create-policy-4.png)  
5. 选择“仅业务数据”分组框中的“+添加”链接：    
   ![登录](./media/prevent-data-loss/create-policy-5.png)  
6. 从“添加服务”页中选择“SharePoint”和“Salesforce”服务：  
   ![登录](./media/prevent-data-loss/create-policy-6.png)  
7. 选择“添加服务”按钮，添加允许共享业务数据的服务：    
   ![登录](./media/prevent-data-loss/create-policy-7.png)  
8. 选择“保存策略”：  
   ![登录](./media/prevent-data-loss/create-policy-8.png)  
9. 片刻之后，新 DLP 策略将显示在数据丢失防护策略列表中：  
   ![登录](./media/prevent-data-loss/create-policy-9.png)  
10. **（可选）**向团队发送一封电子邮件或其他通讯，提醒他们有新的 DLP 策略可用。

祝贺你，现已创建一个允许应用在 SharePoint 与 Saleforce 之间共享数据，并阻止与其他任何服务共享数据的 DLP 策略。  

**注意**：将服务添加到一个数据组会自动将该服务从其他数据组中删除。 例如，如果 Twitter 当前位于“仅业务数据”数据组，并且你不希望允许与 Twitter 共享业务数据，则只需将 Twitter 服务添加到“不允许业务数据”数据组。 这将从“仅业务数据”数据组中删除 Twitter。  

## <a name="data-sharing-violations"></a>数据共享冲突
假定已创建上述 DLP 策略，如果某个用户创建的流在 Salesforce（位于“仅业务数据”数据组中）与 Twitter（位于“不允许业务数据”组中）之间共享数据，系统会通知该用户该流“已暂停”，因为这与已创建的防数据丢失策略冲突。  
![创建流](./media/prevent-data-loss/10.png)  

如果用户因流暂停而与你联系，需考虑下述事项：  

1. 在此示例中，如果因正当业务原因而需要在 SharePoint 和 Twitter 之间共享业务数据，则可编辑 DLP 策略。  
2. 要求用户按 DLP 策略编辑流。  
3. 要求用户在决定是否在这两个实体之间共享数据之前，让流保持“已暂停”状态。  

## <a name="find-a-dlp-policy"></a>查找 DLP 策略
### <a name="admins"></a>管理员
管理员可以从管理中心使用搜索功能查找特定的 DLP 策略。  

**注意：**管理员应该发布所有 DLP 策略，以便组织中的用户在创建流之前，意识到存在这些策略。

### <a name="makers"></a>创建者
如果你没有管理员权限并想要详细了解组织中的 DLP 策略，请与管理员联系。 也可以通过[创建者环境主题](environments-overview-maker.md)了解详细信息  

**注意：**只有管理员可以编辑或删除 DLP 策略。  

## <a name="edit-a-dlp-policy"></a>编辑 DLP 策略
1. 浏览到 https://admin.flow.microsoft.com 启动管理中心。  
2. 在启动的管理中心内，选择左侧的“数据策略”链接。  
   ![登录](./media/prevent-data-loss/2.png)  
3. 搜索现有 DLP 策略的列表，选择要编辑的策略旁边的编辑按钮：  
   ![登录](./media/prevent-data-loss/3.png)  
4. 做出所需的更改。 例如，可以修改环境或者数据组中的服务。  
5. 选择“保存策略”保存所做的更改：  
   ![登录](./media/prevent-data-loss/create-policy-8.png)  

该策略现已更新。 在数据丢失防护策略列表中找到该策略并检查其属性，即可确认是否对它做了更改。   

**注意：**环境管理员可以查看租户管理员创建的 DLP 策略，但无法编辑这些策略。  

## <a name="delete-a-dlp-policy"></a>删除 DLP 策略
1. 浏览到 https://admin.flow.microsoft.com 启动管理中心。  
2. 在启动的管理中心内，选择左侧的“数据策略”链接。  
   ![登录](./media/prevent-data-loss/2.png)  
3. 搜索现有 DLP 策略的列表，选择要删除的策略旁边的删除按钮：  
   ![登录](./media/prevent-data-loss/3-delete.png)  
4. 选择“删除”按钮，确认你确实想要删除该策略：  
   ![登录](./media/prevent-data-loss/4.png)  

该策略现已删除。 在左侧选择“数据策略”链接并查看策略列表，即可确认该策略是否不再列在数据丢失防护策略列表中。   

## <a name="dlp-policy-permissions"></a>DLP 策略权限
只有租户管理员与环境管理员可以创建和修改 DLP 策略。 在[环境主题](environments-overview-admin.md)中了解有关权限的详细信息。  

## <a name="next-steps"></a>后续步骤
* [了解有关环境的详细信息](environments-overview-admin.md)  
* [了解有关 Microsoft Flow 的详细信息](getting-started.md)  
* [了解有关管理中心的详细信息](introduction-to-the-admin-center.md)  

