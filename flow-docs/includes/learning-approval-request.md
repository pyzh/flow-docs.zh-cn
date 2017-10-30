在上一主题中，了解了如何基于 SharePoint 列表中存储的推文生成审批过程。  在本主题中，将了解当审批者收到新审批请求时的大致体验。 

## <a name="create-and-process-a-request"></a>创建和处理请求
我们需要先将项添加到 SharePoint 列表，然后才能处理该项的批准请求。

1. 打开 SharePoint 列表“Contoso 推文”，它已在上一主题中进行配置。  选择“新建”来创建新推文。 
   
    ![SharePoint 列表](./media/learning-approval-request/sharepoint-list-home.png)
2. 将以下值添加到字段，然后选择“保存”。
   
   * **标题** – 提升
   * **推文内容** – 查看 Contoso Flooring 的新行 #ohsocontoso
   * **推文日期** – 今天的日期
     
     ![SharePoint 新项](./media/learning-approval-request/sharepoint-new-tweet.png)
3. 在 **Microsoft Flow** 中，选择“我的流”。 
4. 选择“批准后，将列表项发布到 Twitter”流（已在上一主题中进行配置），然后选择“运行历史记录”下的运行流。
   
    ![运行历史记录](./media/learning-approval-request/run-history.png)
5. 选择“当创建新项时”触发器。 确认刚创建的列表项的信息已显示。
   
    ![流触发器](./media/learning-approval-request/approval-flow.png)
6. 在 **Outlook** 中，打开收件箱中的自动审批邮件，然后选择“批准”。 
   
    ![Outlook 请求](./media/learning-approval-request/outlook-mail.png)
7. 在“审批中心”中，查看请求的详细信息、添加注释，然后选择“确认”。 
   
    ![审批中心](./media/learning-approval-request/approval-center.png)
8. 在 **SharePoint** 中，刷新“Contoso 推文”列表，确认“审批状态”为“是”，并确认输入的注释已显示。 
   
    ![SharePoint 刷新列表](./media/learning-approval-request/sharepoint-list-approved.png)

在本主题中，从审批者的角度，了解了从接收审批请求电子邮件到在审批中心处理请求的体验。

