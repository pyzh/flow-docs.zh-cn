---
title: "将 Azure Active Directory 与自定义连接器配合使用 | Microsoft Docs"
description: "了解如何使用 Azure Active Directory 身份验证为 Azure 资源管理器创建自定义连接器。"
services: 
suite: flow
documentationcenter: 
author: msftman
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/03/2016
ms.author: deonhe
ms.openlocfilehash: 791a44a681ef70ead495bf46623657b2b75cfb65
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="use-azure-active-directory-with-a-custom-connector-in-microsoft-flow"></a>在 Microsoft Flow 中将 Azure Active Directory 与自定义连接器配合使用
可以通过 Azure 资源管理器 (ARM) 在 Azure 上管理解决方案的组件，例如数据库、虚拟机和 Web 应用。 本教程介绍如何在 Azure Active Directory 中启用身份验证，将其中一个 ARM API 注册为自定义连接器，然后在 Microsoft Flow 中连接到该连接器。 若需将 Azure 资源作为流的一部分进行管理，则这样做会很有用。 有关 ARM 的详细信息，请参阅 [Azure 资源管理器概述](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview)。

## <a name="prerequisites"></a>先决条件
* [Azure 订阅](https://azure.microsoft.com/free/)。
* [Microsoft Flow 帐户](https://flow.microsoft.com)。
* 本教程使用的[示例 OpenAPI 文件](https://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json)。

## <a name="enable-authentication-in-azure-active-directory"></a>在 Azure Active Directory 中启用身份验证
首先需创建 Azure Active Directory (AAD) 应用程序，在调用 ARM API 终结点时执行身份验证。

1. 登录到 [Azure 门户](https://portal.azure.com)。  如果有多个 Azure Active Directory 租户，请查看右上角的用户名，确保登录到正确的目录。
   
    ![用户名](./media/customapi-azure-resource-manager-tutorial/current-user.png)
2. 在左侧菜单上，单击“更多服务”。  在“筛选器”文本框中，键入“Azure Active Directory”，然后单击“Azure Active Directory”。
   
    ![Azure Active Directory](./media/customapi-azure-resource-manager-tutorial/azureaad.png)
   
    此时会打开“Azure Active Directory”边栏选项卡。   
3. 在“Azure Active Directory”边栏选项卡的菜单中，单击“应用注册”。
   
    ![应用注册](./media/customapi-azure-resource-manager-tutorial/azureapplication.png)
4. 在已注册应用程序的列表中，单击“添加”。
   
    ![“添加”按钮](./media/customapi-azure-resource-manager-tutorial/add-app-btn.png)   
5. 为应用程序键入一个名称，让“Web 应用/API”处于选中状态，然后键入 `https://login.windows.net` 作为“登录 URL”。  单击“创建”。  
   
    ![新建应用窗体](./media/customapi-azure-resource-manager-tutorial/newapplication.png)
6. 单击列表中的新应用程序。
   
    ![列表中的新建应用](./media/customapi-azure-resource-manager-tutorial/newapplication2.png)
   
    此时会打开“已注册应用”边栏选项卡。  记下“应用程序 ID”。  以后需要该 ID。
7. “设置”边栏选项卡也应已打开。  如果没有打开，请单击“设置”按钮。
   
    ![“设置”按钮](./media/customapi-azure-resource-manager-tutorial/settings-btn.png)
8. 在“设置”边栏选项卡中，单击“答复 URL”。 在 URL 列表中添加 `https://msmanaged-na.consent.azure-apim.net/redirect`，然后单击“保存”。
   
    ![答复 URL](./media/customapi-azure-resource-manager-tutorial/reply-urls.png)
9. 回到“设置”边栏选项卡，单击“所需权限”。  在“所需权限”边栏选项卡中，单击“添加”。
   
    ![所需权限](./media/customapi-azure-resource-manager-tutorial/permissions.png)
   
    此时会打开“添加 API 访问权限”边栏选项卡。
10. 单击“选择 API”。 在打开的边栏选项卡中，单击 Azure 服务管理 API 的选项，然后单击“选择”。
    
    ![选择 API](./media/customapi-azure-resource-manager-tutorial/permissions2.png)
11. 单击“选择权限”。  在“委派权限”下，单击“作为组织用户访问 Azure 服务管理”，然后单击“选择”。
    
    ![委派的权限](./media/customapi-azure-resource-manager-tutorial/permissions3.png)
12. 在“添加 API 访问权限”边栏选项卡中，单击“完成”。
13. 回到“设置”边栏选项卡，单击“密钥”。  在“密钥”边栏选项卡中，键入密钥的说明，选择过期时间，然后单击“保存”。  此时会显示新密钥。  记下密钥值，因为以后也需要该值。  现在可以关闭 Azure 门户。
    
    ![创建密钥](./media/customapi-azure-resource-manager-tutorial/configurekeys.png)

## <a name="add-the-connection-in-microsoft-flow"></a>在 Microsoft Flow 中添加连接
配置 AAD 应用程序以后，即可添加自定义连接器。

1. 在 [Microsoft Flow Web 应用](https://flow.microsoft.com/)中，单击页面右上角的“设置”按钮（齿轮图标）。  然后，单击“自定义连接器”。
   
    ![查找自定义连接器](./media/customapi-azure-resource-manager-tutorial/finding-custom-apis.png)  
2. 单击“创建自定义连接器”。  
   
    系统将提示输入 API 的属性。  
   
   | 属性 | 说明 |
   | --- | --- |
   | 名称 |在页面顶部，单击“无标题”并指定流的名称。 |
   | OpenAPI 文件 |浏览到[示例 ARM OpenAPI 文件](https://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json)。 |
   | “上载 API”图标 |单击“上载图标”，选择图标的图像文件。 可以使用大小不到 1 MB 的任何 PNG 或 JPG 图像。 |
   | 说明 |键入自定义连接器的说明（可选）。 |
   
    ![创建自定义连接器](./media/customapi-azure-resource-manager-tutorial/create-custom-api.png)  
   
    选择“继续”。
3. 在下一个屏幕上，由于 OpenAPI 文件使用 AAD 应用程序进行身份验证，因此需为 Flow 提供该应用程序的一些信息。  在“客户端 ID”下，键入此前记下的 AAD **应用程序 ID**。  对于客户端机密，请使用**密钥**。  最后，键入 `https://management.core.windows.net/` 作为“资源 URL”。
   
   > [!IMPORTANT]
   > 请务必包括资源 URL（如上面所写的那样），包括尾部的反斜杠。
   > 
   > 
   
    ![OAuth 设置](./media/customapi-azure-resource-manager-tutorial/oauth-settings.png)
   
    输入安全信息后，单击位于页面顶部的流名称旁边的复选标记 (**&#x2713;**) 创建自定义连接器。
4. 自定义连接器现已显示在“自定义连接器”下面。
   
    ![可用的 API](./media/customapi-azure-resource-manager-tutorial/list-custom-apis.png)  
5. 注册自定义连接器后，必须与该自定义连接器建立连接才能在应用和流中使用它。  单击自定义连接器名称右侧的“+”，然后完成登录屏幕上的操作。

> [!NOTE]
> 示例 OpenAPI 没有定义整套 ARM 操作，目前只包含[列出所有订阅](https://msdn.microsoft.com/library/azure/dn790531.aspx)操作。  可以使用[在线 OpenAPI 编辑器](http://editor.swagger.io/)编辑此 OpenAPI，或者创建另一 OpenAPI 文件。
> 
> 此过程可以用来访问任何 REST 样式的 API，只要该 API 使用 AAD 进行身份验证即可。
> 
> 

## <a name="next-steps"></a>后续步骤
有关如何创建流的详细信息，请参阅 [Start to build with Microsoft Flow](get-started-logic-flow.md)（开始使用 Microsoft Flow 进行生成）。

若要提问有关自定义连接器的问题或进行评论，请[加入我们的社区](https://aka.ms/flow-community)。

