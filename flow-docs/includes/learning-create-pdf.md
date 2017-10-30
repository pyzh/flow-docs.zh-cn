本主题介绍 Contoso Flooring 如何使用 Microsoft Flow 将文档自动转换为标准格式，然后在 SharePoint Online 中存储它们，以在云中妥善保管。 将创建一个流，用于在新文件添加到 OneDrive for Business 文件夹时进行检测，然后将该文件转换为 PDF 并存储到 SharePoint Online 文件夹中。 

## <a name="prerequisites"></a>先决条件
对于此方案，需要一个 PDF 转换服务 **Muhimbi** 的帐户。 如果尚未拥有 Muhimbi 帐户，可以注册 [30 天免费试用](http://www.muhimbi.com/Products/PDF-Converter-for-SharePoint/Products-PDF-Converter-for-SharePoint-Free-Trial.aspx)。 按照页面上的说明通过 SharePoint Online 站点部署应用。 

## <a name="create-the-source-and-target-folders"></a>创建源和目标文件夹
首先，需要在 OneDrive for Business 和 SharePoint Online 上创建源和目标文件夹。 

1. 在 OneDrive for Business 中的“文件”下，创建名为“已完成的文档”的文件夹。 
   
    ![](./media/learning-create-pdf/onedrive-folder.png)
2. 在 SharePoint Online 中的“共享文档”中，创建名为“PDF - 已完成文件”的文件夹。 
   
    ![](./media/learning-create-pdf/sharepoint-folder.png)

## <a name="create-the-flow"></a>创建流
1. 在 Microsoft Flow 中，选择“我的流”，然后选择“从空白创建”。 
   
    ![](./media/learning-create-pdf/create-blank-flow.png)
2. 选择“搜索数百个连接器和触发器”。
3. 搜索“OneDrive”，选择“OneDrive for Business”，然后选择触发器“OneDrive for Business - 当创建文件时”。 在“文件夹”中，选择文件夹图标，然后选择在上一步中创建的“已完成的文档”文件夹。 
   
    ![](./media/learning-create-pdf/onedrive-trigger.png)
4. 选择“新建步骤”，然后选择“添加操作”。 
   
    ![](./media/learning-create-pdf/new-action.png)
5. 搜索“Muhimbi”，选择“Muhimbi PDF”连接器，然后选择操作“Muhimbi PDF - 转换文档”。
   
    ![](./media/learning-create-pdf/muhimbi-action.png)
6. 此时，可能收到来自 Microsoft Flow 的对 Muhimbi 进行身份验证的提示。 需要使用 **SharePoint 租户 ID** 注册 Muhimbi，以便使 Microsoft Flow 使用 Muhimbi 服务。 
   
   1. 若要查找租户 ID，请在 SharePoint Online 中选择“设置”齿轮图标，然后选择“站点设置”。
   2. 在“网站集管理”下，选择“网站集应用权限”。 租户 ID 是任何应用一览中紧跟在“**@**”符号之后的标识符。 
      
       ![](./media/learning-create-pdf/tenant-id.png)
7. 在“转换文档”操作中，设置以下值：
   
   * **源文件名**：在动态内容列表中，选择“文件名”。
   * **源文件内容**：在动态内容列表中，选择“文件内容”。
   * **输出格式**：从下拉菜单中，选择“PDF”。
     
     ![](./media/learning-create-pdf/muhimbi-configuration.png)

到目前为止，已为流配置了以下步骤： 

1. 每当有新文件添加到特定 OneDrive for Business 文件夹时，都会触发流 
2. Muhimbi 服务将该文件转换为 PDF。 

在最后一步中将添加一个操作，用于将 PDF 文档移动到 SharePoint Online 文件夹，以供团队访问。  

1. 选择“新建步骤”，然后选择“添加操作”。  搜索“SharePoint”，然后选择“SharePoint - 创建文件”操作。 
   
    ![](./media/learning-create-pdf/sharepoint-create-file.png)
2. 在“创建文件”操作中，设置以下值：
   
   * **站点地址**：SharePoint 站点的 URL。  
   * **文件夹路径**：选择文件夹图标，然后导航到“PDF - 完成的文件”文件夹。
   * **文件名**：从“转换文档”的动态内容列表中，选择“基文件名”，然后添加“.pdf”，这样它将保存在 SharePoint 中并带有文件扩展名。 
   * **文件内容**：从“转换文档”的动态内容列表中，选择“处理的文件内容”。
3. 选择页面顶部的“创建流”保存工作。
   
    ![](./media/learning-create-pdf/sharepoint-configure-file.png)

## <a name="test-the-flow"></a>测试流
1. 若要测试流，请将新文件添加到 OneDrive for Business 中“完成的文档”文件夹。 
2. 在流中，选择“我的流”，然后选择新流以查看运行历史记录。 默认情况下，该流配置为每隔五分钟运行。 
3. 流运行后，验证已转换为 PDF 的文件，并且已将其保存到 SharePoint 的“PDF - 完成的文件”文件夹。 
   
    ![](./media/learning-create-pdf/test-the-flow.png)

