---
title: "使用 Dynamics 365（联机）创建流 | Microsoft Docs"
description: "通过使用 Dynamics 365 连接和 Microsoft Flow 创建有用的工作流"
services: 
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
ms.openlocfilehash: 5ef3de417b1557644ce9bfcd935353e017ceb676
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>通过使用 Dynamics 365（联机）创建流
通过使用 Dynamics 365 连接器可以创建流，这些流在 Dynamics 365 或其他某个服务中的事件发生时启动，然后将在 Dynamics 365 或其他某个服务中执行某项操作。 

在 Microsoft Flow 中，可以在最喜欢的应用和服务之间设置自动化工作流，以便同步文件、获取通知、收集数据等。 有关详细信息，请参阅 [Microsoft Flow 入门](getting-started.md)。

## <a name="create-a-flow-from-a-template"></a>通过模板创建流
可以使用许多可用模板之一来创建流，示例如下：

* 当在 Dynamics 365 中创建对象后，在 SharePoint 中创建一个列表项。
* 从 Excel 表创建 Dynamics 365 潜在客户记录。
* 将 Dynamics 365 帐户复制到 Dynamics 365 for Operations 中的客户。

若要通过模板创建一个流，请执行下列步骤。

1. 登录到 [Microsoft Flow 网站](https://flow.microsoft.com/)。
2. 单击或点击“服务”，然后单击或点击“Dynamics 365”。
3. 有一些模板可供使用。 若要开始，请选择所需的模板。

## <a name="create-a-task-from-a-lead"></a>从潜在客户创建任务
如果模板不适用于你的需求，请从头开始创建流。 本演练演示了如何每当在 Dynamics 365 中创建潜在客户时在 Dynamics 365 中创建任务。

1. 登录到 [Microsoft Flow 网站](https://flow.microsoft.com/)。
2. 单击或点击“我的流”，然后单击或点击“从空白创建”。
3. 在流触发器的列表中，单击或点击“Dynamics 365 - 创建记录时”。
4. 如果系统提示，请登录到 Dynamics 365。
5. 在“组织名称”下，选择想要流侦听的 Dynamics 365 实例。
6. 在“实体名称”下，选择想要侦听的实体，这将充当启动流的触发器。
   
     对于本演练，请选择“潜在客户”。
   
    ![流详细信息](./media/connection-dynamics365/flow-details.png)
7. 单击或点击“新建步骤”，然后单击或点击“添加操作”。
8. 单击或点击“Dynamics 365 – 创建新记录”。
9. 在“组织名称”下，选择想要流创建记录的 Dynamics 365 实例。 请注意，它不一定是触发了事件的同一实例。
10. 在“实体名称”下，选择在事件发生时将创建一条记录的实体。
    
     对于本演练，请选择“任务”。
11. 此时将显示“主题”框。 单击或点击它时，将显示动态内容窗格，在其中可以选择以下字段之一。
    
    * **姓氏**。 如果选择此字段，潜在客户的姓氏将在创建任务时插入到该任务的“主题”字段。
    * **标题**。 如果选择此字段，潜在客户的“标题”字段将在创建任务时插入到该任务的“主题”字段。
    
    对于本演练，请选择“标题”。
    
    ![为流添加标题](./media/connection-dynamics365/flow-addtopic.png)
    
    > 提示：在动态内容窗格中，单击或点击“查看更多”可显示与实体关联的多个字段。 例如，还可以使用潜在客户的“公司名称”、“客户”、“说明”或“电子邮件”字段填充该任务的“主题”字段。
    > 
    > 
12. 单击或点击“创建流”。

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>从 Dynamics 365 任务创建 Wunderlist 任务
本演练演示了如何每当在 Dynamics 365 中创建任务时在 [Wunderlist](http://www.wunderlist.com) 中创建任务。 Wunderlist 是一种基于 Internet 的服务，可用于创建待办事项列表、添加提醒或跟踪事项。

1. 登录到 [Microsoft Flow 网站](https://flow.microsoft.com/)。
2. 单击或点击“我的流”，然后单击或点击“从空白创建”。
3. 在流触发器的列表中，单击或点击“Dynamics 365 - 创建记录时”。
4. 在“组织名称”下，选择想要流侦听的 Dynamics 365 实例。
5. 在“实体名称”下，选择想要侦听的实体，这将充当用于启动流的触发器。
   
    对于本演练，请选择“任务”。
6. 单击或点击“新建步骤”，然后单击或点击“添加操作”。
7. 键入“创建任务”，然后单击或点击“Wunderlist – 创建任务”。
8. 在“列表 ID”下，选择“收件箱”。
9. 在“标题”下，选择动态内容窗格中的“主题”。
10. 单击或点击“创建流”。  

## <a name="specify-advanced-options"></a>指定高级选项
向流添加步骤时，可以单击或点击“显示高级选项”来添加筛选器或 Order By 查询，从而控制在流中筛选数据的方式。

例如，可以使用筛选器查询来仅仅检索活跃的联系人，然后可以按姓氏对其进行排序。 为此，请输入 OData 筛选器查询 **statuscode eq 1**，然后从动态内容窗格选择“姓氏”。 有关筛选器和 Order By 查询的详细信息，请参阅 [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) 和 [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2)。

  ![流的 orderby 查询](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>使用高级选项时的最佳做法
向字段添加值时，无论是键入值还是从动态内容窗格中选择值，都必须与字段类型匹配。

| 字段类型 | 如何使用 | 在哪里可以找到 | 名称 | 数据类型 |
| --- | --- | --- | --- | --- |
| 文本字段 |文本字段需要单行文本或作为文本类型字段的动态内容。 示例包括“类别”和“子类别”字段。 |**设置** > **自定义** > **自定义系统** > **实体** > **任务** > **字段** |**类别** |**单行文本** |
| 整数字段 |某些字段需要整数或作为整数类型字段的动态内容。 示例包括“完成百分比”和“持续时间”。 |**设置** > **自定义** > **自定义系统** > **实体** > **任务** > **字段** |**percentcomplete** |**整数** |
| 日期字段 |某些字段需要以 mm/dd/yyyy 格式输入的日期或作为日期类型字段的动态内容。 示例包括“创建日期”、“开始日期”、“实际开始时间”、“上一暂候时间”、“实际结束时间”和“截止日期”。 |**设置** > **自定义** > **自定义系统** > **实体** > **任务** > **字段** |**createdon** |**日期和时间** |
| 需要记录 ID 和查找类型的字段 |某些引用另一个实体记录的字段需要记录 ID 和查找类型。 |**设置** > **自定义** > **自定义系统** > **实体** > **帐户** > **字段** |**accountid** |**主键** |

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>更多需要记录 ID 和查找类型的字段示例
此处对上一个表进行扩展，提供了更多不使用从动态内容列表中选择的值的字段示例。 相反，这些字段需要在 PowerApps 中输入到字段的记录 ID 和查找类型。

* **所有者**和**所有者类型**。
  
  * “所有者”字段必须是有效的用户或团队记录 ID。
  * “所有者类型”必须是 **systemusers** 或 **teams**。
* **客户**和**客户类型**。
  
  * “客户”字段必须是有效的帐户或联系人记录 ID。
  * “客户类型”必须是 **accounts** 或 **contacts**。
* **相关项**和**相关项类型**。
  
  * “相关项”字段必须是有效的记录 ID，如帐户或联系人记录 ID。
  * “相关项类型”必须是记录的查找类型，如 **accounts** 或 **contacts**。

此示例将与记录 ID 对应的帐户记录添加到任务的“相关项”字段中，从而添加该帐户记录。

  ![流 recordId 和类型帐户](./media/connection-dynamics365/flow-recordid-account.png)

此示例还基于用户的记录 ID 将任务分配给特定用户。

  ![流 recordId 和类型用户](./media/connection-dynamics365/flow-recordid-user.png)

若要查找记录的 ID，请参阅本主题中后面的[查找记录 ID](#find-the-record-id)。

> 重要说明：如果字段有“仅限内部使用”的说明，则这些字段不应包含值。 这些字段包括“遍历的路径”、“其他参数”和“时区规则版本号”。
> 
> 

## <a name="find-the-records-id"></a>查找记录 ID
1. 在 Dynamics 365 Web 应用程序中，打开一个记录，如帐户记录。
2. 在操作工具栏上，单击或点击“弹出”
   “弹出记录”![](./media/connection-dynamics365/popout.png)（或单击或点击“通过电子邮件发送链接”，以将完整的 URL 复制到默认电子邮件程序）。
   
    在 Web 浏览器的地址栏中，该 URL 包含 %7b 和 %7d 编码字符之间的记录 ID。
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>相关主题
[流故障排除](fix-flow-failures.md)

[有关组织中的流的问答](organization-q-and-a.md)

[常见问题](frequently-asked-questions.md)

