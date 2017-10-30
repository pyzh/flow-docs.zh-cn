欢迎回到 Microsoft Flow 的引导式学习。 在本课中，你将更深入地了解 Microsoft Flow 环境，并且可以**生成你的第一个流**。

Microsoft Flow 入门很简单，因为有大量的**模板可供选择**，这些模板可帮助你以更有意义的方式连接到已经在使用的服务。  

## <a name="microsoft-flow-templates"></a>Microsoft Flow 模板
看一看 [ Microsoft Flow 网站](https://ms.flow.microsoft.com)，并打开“模板”菜单。 随着在列表中滚动，将看到 Microsoft Flow 支持连接到许多服务。

![Flow 网站 -> 模板列表](./media/learning-create-a-flow/template-list.png)

## <a name="choose-a-template"></a>选择模板
通过电子邮件**搜索附件**可能很耗时，此流通过**将所有电子邮件附件存储**到 OneDrive 中的文件夹中来节省时间。

选择“将 Office 365 电子邮件附件保存到 OneDrive for Business”模板。

![Office 365 电子邮件](./media/learning-create-a-flow/office-365-email.png)

## <a name="create-and-administer-a-flow"></a>创建和管理流
这是我们的**一键式**模板之一，在这些模板中，只需回答**生成流所必需的**相关问题。

在模板图形上，有一个关于**模板的功能和成功的必备条件**的**说明**。

将要求为 **Office 365 Outlook** 和 **SharePoint** 服务**提供凭据**。 如果定期使用这两种服务，那么已经登录到它们。

![保存 Office 365 电子邮件](./media/learning-create-a-flow/save-flow-office-description.png)

1. 选择“创建流”。
   
    ![单击“创建流”](./media/learning-create-a-flow/click-create-flow.png)
   
    然后将看到结果。 
   
    ![创建成功](./media/learning-create-a-flow/create-successful.png)
   
    流在 OneDrive 上有一个**已创建的文件夹**，它现在将在该文件夹中自动放置发送到工作电子邮件地址的**每个附件**。
2. 打开“我的流”。
   
    ![打开“我的流”](./media/learning-create-a-flow/click-my-flows.png)
3. 选择“刚刚创建的流”查看它的工作原理。
   
    ![选择该流](./media/learning-create-a-flow/click-the-flow.png)
4. 将看到一个**绿色复选标记**，指示**流已成功**。 选择“已成功”，查看运行历史记录和结果。
   
    ![流成功](./media/learning-create-a-flow/flow-successful.png)
   
    **流的所有部分**均已成功。 
   
    ![运行历史记录](./media/learning-create-a-flow/run-history.png)

## <a name="important-concepts-in-microsoft-flow"></a>Microsoft Flow 中的重要概念
在生成流时需要知道的一些事项。 每个流都有两个关键部分：**触发器**和**一个或多个操作**。 

可以将**触发器**视为流的起始操作，可以是上述的**收到新电子邮件时**，如果恰巧在使用 SharePoint，则可以是**添加新项时**。 如果使用名为**重复**的触发器，那么它还可以是固定的计划，这将在稍后进行介绍。

操作是希望在**调用触发器时**发生的**活动**。 例如，**创建文件**将在 OneDrive 中重新创建文件。

![收到新电子邮件时的操作](./media/learning-create-a-flow/trigger-or-action.png)

其他操作可以是发送**电子邮件**、发布**推文**、启动**审批**，等等。
从头开始构建自己的流时，所有这些稍后都将涉及到。 

## <a name="next-lesson"></a>下一课
下一课将介绍 Microsoft Flow 移动应用及其功能。 

