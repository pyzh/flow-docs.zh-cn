---
title: 添加高级选项和多个操作 | Microsoft Docs
description: 扩展一个流，使之包括高级选项（例如将电子邮件的优先级设置为高），并为同一事件添加其他操作。
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2017
ms.author: stepsic
ms.openlocfilehash: f6c936cbf5a2bd481adb52ec9b01545fb9ba7b0b
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23442109"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>向流添加多个操作和高级选项
为同一触发器添加一个或多个高级选项和多个操作，对流进行自定义。 例如，添加一个将电子邮件按高优先级发送的高级选项。 除了在向 SharePoint 列表添加项目时发送邮件以外，还可以在 Dropbox 中创建一个包含相同信息的文件。

## <a name="prerequisites"></a>先决条件
* [创建流](get-started-logic-flow.md)

## <a name="add-another-action"></a>添加其他操作
在此过程中，需在流中间添加操作。 此操作会将文件保存在 Dropbox 中，将项目在列表中存档。

1. 在 [flow.microsoft.com](https://flow.microsoft.com) 的顶部导航栏中选择“我的流”。
2. 在流列表中，选择要编辑的流。
3. 选择“新建步骤”，然后选择“添加操作”。
   
    ![折叠添加](./media/multi-step-logic-flow/add-action.png)
4. 在包含可用操作的列表中，搜索“创建文件”，然后选择“Dropbox - 创建文件”。
   
    ![搜索“创建文件”](./media/multi-step-logic-flow/create-file-search.png)
5. 如果出现提示，请提供 Dropbox 凭据。
6. 选择“文件夹路径”框右侧的文件夹图标。
7. 查找并选择你想要将新文件放置到的文件夹。
   
    ![搜索“创建文件”](./media/multi-step-logic-flow/create-file-folder.png)
8. 将新文件的名称输入到“文件名”框中。 请务必将扩展名（如“.txt”）追加到文件名。 在这里，让我们在文件的名称中使用 **TweetId** 来确保文件的唯一性。 可能必须选择“查看更多”才能找到“TweetId”标记。
9. 通过在“文件内容”框中键入内容，添加你希望文件包含的文本。 还可以将标记添加到“文件内容”框中。
   
    ![文件名和内容](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > 如果为文件提供一个与现有文件（在所选文件夹中）名称匹配的名称，则将覆盖现有文件。
   > 
   > 
10. 选择位于屏幕顶部的菜单上的“更新流”。
11. 发送包含指定关键字的推文。
    
     在一分钟内，Dropbox 帐户中会创建一个文件。

## <a name="reorder-or-delete-an-action"></a>对操作重新排序或将其删除
* 在 Dropbox 中创建文件以后，若要接收电子邮件，请移动 Dropbox 操作，方法是将其标题栏拖至电子邮件操作上方。 在触发器（“发布新推文时”）和电子邮件操作之间的箭头上方释放该 Dropbox 操作。 （光标指示指示该操作是否已正确定位。）
  
  > [!NOTE]
  > 如果使用了某个步骤的输出，则不能将该步骤移至另一个步骤前面。
  > 
  > 
  
    ![删除菜单](./media/multi-step-logic-flow/draggingaction.png)
* 若要删除某个操作，请选择要删除操作所对应的标题栏右侧旁边的省略号 (...)，然后选择“删除”，再选择“确定”。
  
    ![删除菜单](./media/multi-step-logic-flow/deletemenu.png)
  
     **注意：** 如果在流中的任何位置使用某个操作的任何输出，则不能删除该操作。 请先删除字段中的这些输出，然后即可删除该操作。

## <a name="add-advanced-options"></a>添加高级选项
开始时请使用包含“发送电子邮件”操作的流。

1. 选择“显示高级选项”，它位于“发送电子邮件”卡的底部。
   
     然后，你将看到用于发送电子邮件的高级选项。
   
    ![Sharepoint 触发器](./media/multi-step-logic-flow/advanced.png)
2. 从“重要性”列表中选择“高”，然后选择“隐藏高级选项”以隐藏高级选项。
3. 选择位于屏幕顶部的菜单上的“更新流”。
   
     此步骤将保存更改。

