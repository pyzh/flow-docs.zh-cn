---
title: 了解如何通过按钮流实现重复任务的自动化操作和运行 | Microsoft Docs
description: 按钮流简介。
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
ms.date: 01/30/2017
ms.author: deonhe
ms.openlocfilehash: 558570733819e1fde6c1845ed5ca9debe9232c88
ms.sourcegitcommit: f0202f74ba9a2282a670a1751462f598a5ea0ce5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="introducing-button-flows"></a>按钮流简介
## <a name="what-are-button-flows"></a>什么是按钮流？
我们都希望只需点击几下按钮就可以运行许多重复性任务。 例如，你可能需要快速地向团队发送电子邮件，提醒他们参加每天的团队同步会议，也可能需要开始新的 Visual Studio Online 代码库生成，因为你已获得通知，知道今天不会再计划其他签入。 使用按钮流，只需在移动设备上点击一下按钮，即可完成此类任务以及许多其他的任务。

**注意**：可以从移动设备或 Flow 门户创建按钮流。  
  ![概略图](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>为什么创建按钮？
创建按钮即可随时随地通过移动设备轻松地运行重复性任务。 执行按钮可以节省时间，而且，由于任务是自动执行的，发生错误的可能性比手动执行要低。  

## <a name="create-a-button"></a>创建按钮
### <a name="prerequisites"></a>先决条件
* 访问 Flow。 管理员可以为用户提供访问权限。
* 一个有权使用连接器创建按钮的帐户。 例如，若要创建可以访问 Dropbox 的按钮，需要一个 Dropbox 帐户。

### <a name="from-the-portal"></a>从门户
本演练需创建一个按钮，以便启动 Visual Studio Online (VSO) 生成并在生成启动以后向用户发送相关通知。  

1. 选择“显示”下拉列表，然后选择“按钮”类别。 这样会筛选出一系列只能用在按钮流中的模板。  
   ![概略图](./media/introduction-to-button-flows/create-button-1.png)   
2. 从模板列表中选择“在 VSO 中触发新的生成”模板。  
   ![概略图](./media/introduction-to-button-flows/create-button-2.png)  
3. 在“在 VSO 中触发新的生成”页中选择“使用此模板”按钮。   
   ![概略图](./media/introduction-to-button-flows/create-button-3.png)  
4. 如果用户没有登录，系统此时会提示用户登录：  
   ![概略图](./media/introduction-to-button-flows/create-button-4.png)  
5. 用户登录到 Flow 以后，系统会提示其登录到所选模板中使用的连接器。 此示例已在上面的步骤 2 中选择了“在 VSO 中触发新的生成”模板，因此如果尚未登录，则需登录到 VSO（以及所使用的任何其他连接器）：  
   ![概略图](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. 如果同意授权 Flow 访问 VSO 帐户，请选择“接受”按钮。  
   ![概略图](./media/introduction-to-button-flows/create-button-5.png)   
   **注意**：需采取类似方式向每个连接器授权。 准备执行下一步操作时，设计器应如下所示。 选择“继续”按钮继续：  
   ![概略图](./media/introduction-to-button-flows/create-button-6.png)   
7. 现在可以配置要启动的生成的属性了：    
   ![概略图](./media/introduction-to-button-flows/create-button-7.png)  
8. 在“对新生成排队”卡中，选择或输入“帐户名称”、“项目名称”、“生成定义 ID”、“源分支”以及“参数”（可选）：    
   ![概略图](./media/introduction-to-button-flows/create-button-8.png)  
9. 接下来，请在“发送推送通知”卡中配置推送通知的属性。 默认情况下，此推送通知配置为发送显示生成状态的网页的 HTML 链接：  
   ![概略图](./media/introduction-to-button-flows/create-button-9.png)  
10. 选择“创建流”按钮保存按钮流：![概略图](./media/introduction-to-button-flows/create-button-10.png)  
11. 过一会儿就会看到以下成功消息：  
    ![概略图](./media/introduction-to-button-flows/create-button-11.png)  

恭喜，你已创建按钮流! 现在，你可以在 Flow 应用中通过“按钮”选项卡随时随地运行此按钮流。 一按“按钮”即可运行！ Microsoft Flow 移动应用适用于 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows)。

### <a name="from-your-mobile-device"></a>从移动设备
**注意**：本演练显示的是 Android 设备的屏幕，但 iOS 设备上的屏幕和体验是类似的。

在 Flow 应用中：

1. 选择“浏览”选项卡，滚动到“按钮”类别。  
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. 选择“全部查看”链接。 此时会显示所有准备就绪的按钮模板。     
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. 选择“发送电子邮件，提醒团队参加会议”模板    
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. 选择页面底部的“使用此模板”链接。    
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. 用户需登录到此模板使用的所有服务：    
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. 登录到所有服务以后，选择“下一步”链接。      
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. 选择“创建”链接。 在这里还可以查看流并进行相关操作，例如进行电子邮件个性化所需的任何更改。        
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. 几分钟后就会创建好按钮流。 选择“查看我的流”：   
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. 在“我的流”选项卡上查看所有流  
   ![概略图](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

恭喜，你已创建按钮流! 现在，你可以在 Flow 应用中通过“按钮”选项卡随时随地运行此按钮流。 一按“按钮”即可运行！ Flow 应用目前可在 Android 和 iOS 移动设备上使用。  

![概略图](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>触发按钮流
创建按钮流后即可马上运行。 由于只能从 Flow 应用运行按钮流，因此请确保在 Android 或 iOS 移动设备上安装 Flow。  

1. 现在请启动 Flow 应用，点击位于页面底部的“按钮”选项卡，然后点击代表要触发的按钮流的“按钮”：  
   ![概略图](./media/introduction-to-button-flows/trigger-button-1.png)   
2. 查看流运行时的进度：  
   ![概略图](./media/introduction-to-button-flows/trigger-button-2.png)   
3. 最后页面会更新，表明按钮流已完成：  
   ![概略图](./media/introduction-to-button-flows/trigger-button-3.png)   

这就是运行流的整个过程。 

此时会收到推送通知，表明电子邮件已发送。  

## <a name="monitor-your-button-flow-runs"></a>监视按钮流运行
可以在 Flow 应用的“活动”选项卡中监视按钮流：   
![概略图](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**注意**：点击任意活动即可深入查看运行结果，了解运行的情况。  

![概略图](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>管理按钮流
用户对按钮流具有完全控制权限，可以随时随地启用/禁用、编辑或删除按钮。 通过移动应用或 Flow 门户选择“我的流”即可开始管理流。    

在 Flow 应用的“我的流”选项卡上执行以下操作：

1. 选择要管理的流：    
   ![概略图](./media/introduction-to-button-flows/trigger-button-4.png)   
2. 可以点击其中任何一个选项，具体取决于要完成的任务：    
   ![概略图](./media/introduction-to-button-flows/manage-flow-1.png)  
3. 点击“删除流”将流删除。  

**注意**：删除流时，将会删除所有运行历史记录：   
![概略图](./media/introduction-to-button-flows/manage-flow-2.png)   

1. 编辑完按钮流以后，点击“更新”保存所做的更改：   
   ![概略图](./media/introduction-to-button-flows/manage-flow-3.png)   
2. 点击“运行历史记录”，查看特定按钮流的所有运行的结果：    
   ![概略图](./media/introduction-to-button-flows/manage-flow-4.png)  
3. 如果禁用某个流，该流将不再出现在“按钮”选项卡上：    
   ![概略图](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>后续步骤
* [共享按钮流](share-buttons.md)。
* 了解如何在运行按钮流时使用[按钮触发器令牌](introduction-to-button-trigger-tokens.md)发送实时数据。
* 安装适用于 [Android](https://aka.ms/flowmobiledocsandroid)、[iOS](https://aka.ms/flowmobiledocsios) 或 [Windows Phone](https://aka.ms/flowmobilewindows) 的 Microsoft Flow 移动应用。

