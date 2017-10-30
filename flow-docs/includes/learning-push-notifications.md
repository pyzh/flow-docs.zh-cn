对于此流，将生成 **SharePoint** 列表，**Contoso Flooring** 市场营销团队会将其 **Twitter 帖子**和发布日期存储在该列表中。 在此处，将生成可自动通过推文形式发布内容的流。 

## <a name="connect-microsoft-flow-services"></a>连接 Microsoft Flow 服务
在本主题中，将使用 **SharePoint** 和 **Twitter** 服务。 如果对使用的服务不熟悉，首先需要连接到新服务。 

1. 在 Microsoft Flow 中，选择**齿轮图标**，然后选择“连接”，
   
    ![获取连接](./media/learning-push-notifications/2-get-connection.png) 
2. 选择“+ 创建连接”。
   
    ![创建连接](./media/learning-push-notifications/3-create-connection.png) 
3. 向下滚动列表，找到 Twitter 并选择“+”。
   
    ![单击加号](./media/learning-push-notifications/4-click-plus.png)
4. 若要授权 Twitter 帐户，则输入用户名或电子邮件和密码，然后选择“授权应用”。
   
    ![创建 ID 和密码](./media/learning-push-notifications/5-create-id-pswd.png)
5. 若要检查连接，请选择**齿轮图标**和“连接”。
   
    ![我的连接](./media/learning-push-notifications/6-my-connections.png)
   
    应该会看到新的 Twitter 连接和已创建的任何其他连接。 
   
    ![Twitter 连接](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>生成 SharePoint 列表
首先需要为 Contoso Flooring 创建新的 SharePoint Online 列表。 

1. 在 SharePoint Online 中，选择“新建”，然后选择“列表”。
   
    ![创建新列表](./media/learning-push-notifications/1-new-list.png)
2. 将列表命名为“Contoso 推文”。 
3. 清除“在站点导航中显示”复选框，然后选择“创建”。
   
    ![创建列表](./media/learning-push-notifications/2-name-create-list.png)
   
    选择“创建”后，SharePoint 将转至新列表。
4. 默认情况下，列表具有单个列，即“标题”列。 添加另一列并将该列命名为“推文内容”。 推文中所写的内容都将显示在此处。 
   
   1. 选择加号，然后选择“更多...”
      
       ![创建列表](./media/learning-push-notifications/3-add-more-column-types.png)
   2. 选择“多行文本”，然后选择“确定”。
      
       ![创建列表](./media/learning-push-notifications/4-add-column.png)
5. 为推文日期和时间添加一列，并将该列命名为“推文日期”。
   
   1. 与上述“推文内容”一样，选择加号，然后选择“更多...”
      
       ![日期时间列](./media/learning-push-notifications/5-date-time-col.png)
   2. 向下滚动到“日期和时间格式”。 选择“日期和时间”，这样两者均包含在内。
      
       ![日期和时间](./media/learning-push-notifications/6-date-time-must-do.png)
   3. 选择“确定”。 SharePoint 网站中将显示“Contoso 推文”列表，可以向该列表添加新项。

## <a name="build-the-flow"></a>生成流
列表已生成，现在便可以生成流。

### <a name="choose-a-trigger"></a>选择触发器
1. 在 Microsoft Flow 中，转到“我的流”，然后选择“从空白创建”。
   
    ![从空白创建](./media/learning-push-notifications/8-create-from-blank.png)
2. 选择“在创建项时”。
   
    ![添加触发器](./media/learning-push-notifications/9-add-trigger.png)
   
    我们希望能够在新行添加推文内容时引发触发器。
3. 选择 SharePoint 网站，然后选择前面设置的列表“Contoso 推文”。
   
    ![新项已创建](./media/learning-push-notifications/11-set-trigger.png)

好了，触发器已添加。

### <a name="add-an-action-to-delay-posting"></a>添加要延迟发布的操作
1. 选择“+ 新步骤”，然后选择“添加操作”。 
   
    ![添加步骤和操作](./media/learning-push-notifications/12-add-step-and-action.png)
2. 在“日程安排”服务下，选择“延迟截止时间”。 
   
    ![延迟截止时间](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. 设置延迟值。
   
   1. 在“时间戳”字段内单击或点击。 
   2. 当动态内容框打开时，向下滚动到底部，将从 SharePoint 列表看到以下三列：**标题**、**推文日期**和**推文内容**。
   3. 选择“推文日期”。 
      
       ![延迟截止时间时间戳](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       现在，当有人将内容添加到 SharePoint 列表时，会将任何操作延迟到在“推文日期”列中设置的日期和时间。
      
       ![动态时间戳](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>添加操作以发布推文
现在，为流添加要在“推文日期”列中指定的日期和时间执行的其他操作。

1. 选择“+ 新步骤”、“添加操作”，然后搜索 **Twitter**。
   
    ![添加推文](./media/learning-push-notifications/16-add-tweet.png) 
2. 选择操作“Twitter - 发布推文”。
   
    ![发布推文](./media/learning-push-notifications/17-post-tweet.png) 
3. 在“推文文本”字段内单击或点击，然后在动态内容框中选择“推文内容”。 此处是已创建的序列。 
   
    ![推文日期内容](./media/learning-push-notifications/18-tweet-date-content.png)
4. 选择“创建流...”
   
    ![创建流](./media/learning-push-notifications/19-tiny-create.png) 
5. 选择“完成”。
   
    ![单击完成](./media/learning-push-notifications/19-click-done.png)
   
    现在流已完成。
   
    ![流已完成](./media/learning-push-notifications/20-flow-is-done.png)
   
    当在 SharePoint 列表中创建新项时，流会将发布延迟到预先设置的日期。 当满足该日期时，流会将列表内“推文内容”列中的文本发布到 Twitter。

## <a name="next-lesson"></a>下一课
在下一课中，将了解如何使用名为“重复”的触发器**按日程安排运行流**。

