---
title: "注册和使用自定义连接器 | Microsoft Docs"
description: "通过 OpenAPI 和 Postman 在 Microsoft Flow 中注册和使用自定义连接器。"
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: sunayv
ms.openlocfilehash: 94d46b2948f03316162e1c1d45860ae94feb897c
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2017
---
# <a name="register-and-use-custom-connectors-in-microsoft-flow"></a>在 Microsoft Flow 中注册和使用自定义连接器
有了 Microsoft Flow，不使用代码也可以生成工作流。 但在某些情况下，需要扩展 Microsoft Flow 功能，这时就很适合使用 Web 服务。 你的流可以连接到服务、执行操作和取回数据。 如果需要通过 Microsoft Flow 连接到某个 Web 服务，可以将该服务注册为自定义连接器。 此过程让 Microsoft Flow 了解 Web API 的特征，包括所需的身份验证、所支持的操作，以及每项此类操作的参数和输出。

本主题将介绍注册和使用自定义连接器所需的步骤，并将使用 Azure 认知服务[文本分析 API](https://www.microsoft.com/cognitive-services/text-analytics-api)。 该 API 标识你传递给它的文本中的语言、情绪和关键短语。

## <a name="prerequisites"></a>先决条件
* [Microsoft Flow 帐户](https://flow.microsoft.com)。
* JSON 格式的 OpenAPI 2.0（以前称为 Swagger) 文件、指向 OpenAPI 定义的 URL，或者适用于 API 的 Postman Collection。 如果你没有上述任何一项，我们会为你提供指南。
* 用作自定义连接器图标的图像（可选）。

## <a name="steps-in-the-custom-connector-process"></a>自定义连接器过程中的步骤
自定义连接器过程有几个步骤，将在下面简要描述。 本文假设你已经有一个 REST 样式的 API 和某类经身份验证的访问权限，因此我们会在本文后面重点介绍步骤 3-6。 有关步骤 1 和 2 的示例，请参阅[创建适用于 Microsoft Flow 的自定义 Web API](customapi-web-api-tutorial.md)。

1. 使用所选语言和平台**生成 REST 样式的 API**。 对于 Microsoft 技术，建议使用下述选项之一（不过，任何平台均可使用）：
   
   * Azure Functions
   * Azure Web 应用
   * Azure API 应用
2. 使用下述身份验证机制之一**保护 API 的安全**。 可以不经身份验证就访问连接器，但不建议这样做。
   
   * Azure Active Directory。 有关详细信息，请参阅[在 Microsoft Flow 中将 Azure Active Directory 与自定义连接器配合使用](customapi-azure-resource-manager-tutorial.md)。
   * 适用于特定服务（例如 Dropbox、Facebook 和 SalesForce）的 OAuth 2.0
   * 通用 OAuth 2.0
   * API 密钥
   * 基本身份验证
3. 以两种行业标准方式中的一种**描述 API**，方便 Microsoft Flow 连接到该 API。
   
   * OpenAPI 文件
   * Postman Collection
     
     也可在注册过程中的步骤 4 生成 OpenAPI 文件。
4. 在 Microsoft Flow 中通过向导**注册自定义连接器**。在该向导中，可以指定 API 说明、安全细节等信息。
5. 在应用中**使用自定义连接器**。 在应用中创建到连接器的连接，然后调用 API 提供的任何操作，就像在 Microsoft Flow 中调用标准连接一样。
6. **共享自定义连接器**，就像在 Microsoft Flow 中共享其他资源一样。 此步骤为可选，但通常会跨多个应用创建者共享自定义连接器。

## <a name="describe-your-api"></a>描述 API
假设你有一个 API 和某类经身份验证的访问权限，则需通过某种方式对 API 进行描述，以便 Microsoft Flow 能够连接到该 API。 为此，请创建 OpenAPI 文件或 Postman Collection – 这可以从任何 REST API 终结点创建，其中包括：

* 公开发布的连接器。 部分示例包括 [Spotify](https://developer.spotify.com/)、[Uber](https://developer.uber.com/)、[Slack](https://api.slack.com/)、[Rackspace](http://docs.rackspace.com/)，等等。
* 创建并部署到任何云托管提供程序（包括 Azure、Amazon Web Services (AWS)、Heroku、Google Cloud 等）的 API。
* 在网络上部署的自定义业务线 API，前提是该 API 已在公共 Internet 上公开。

OpenAPI 2.0（以前称为 Swagger）和 Postman Collection 使用不同的格式，但二者都是与语言无关的机器可读文档，用于描述 API 的操作和参数：

* 可以根据生成 API 时所基于的语言和平台，使用不同的工具生成这些文档。 如需 OpenAPI 文件的示例，请参阅[文本分析 API 文档](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/export?DocumentFormat=Swagger&ApiName=Azure)。
* 如果还没有适用于 API 的 OpenAPI 文件且不想创建该文件，则仍可使用 Postman Collection 轻松创建自定义连接器。 有关详细信息，请参阅[创建 Postman Collection](postman-collection.md)。
* Microsoft Flow 最终会在后台使用 OpenAPI，因此会将 Postman Collection 分析并转换成 OpenAPI 定义文件。

**注意**：文件大小必须不到 1 MB。

### <a name="getting-started-with-openapi-and-postman"></a>OpenAPI 和 Postman 入门
* 如果不熟悉 OpenAPI，请参阅 swagger.io 站点上的 [Getting Started with OpenAPI](http://swagger.io/getting-started/)（OpenAPI 入门）。
* 如果不熟悉 Postman，请从其站点安装 [Postman 应用](https://www.getpostman.com/apps)。
* 如果 API 是使用 Azure API 应用或 Azure Functions 生成的，请参阅[将 Azure 托管的 API 导出到 PowerApps 和 Microsoft Flow](https://docs.microsoft.com/azure/app-service/app-service-export-api-to-powerapps-and-flow) 以获取详细信息。

## <a name="register-your-custom-connector"></a>注册自定义连接器
现在将使用 OpenAPI 文件或 Postman Collection 在 Microsoft Flow 中注册自定义连接器。

1. 在 [flow.microsoft.com](https://flow.microsoft.com) 的顶栏中，选择用于打开设置菜单的齿轮图标。 选择“自定义连接器”选项。
   
    ![创建自定义连接器](./media/register-custom-api/managecustomapi.png)  
2. 选择“创建自定义连接器”。
   
    ![自定义连接器属性](./media/register-custom-api/newcustomapi.png)
3. 在“常规”选项卡上，根据需要选择创建自定义连接器的方式。
   
   * 上传 OpenAPI
   * 粘贴 OpenAPI URL
   * 上传 Postman Collection V1
     
     ![如何创建自定义连接器](./media/register-custom-api/choosehowtocreate.png)
     
     上传自定义连接器的图标。 “说明”、“主机”和“基 URL”字段通常会自动填充 OpenAPI 文件提供的信息。 如果未自动填充，则可手动向这些字段添加信息。 选择“继续”。
4. 在“安全”选项卡中，输入任何身份验证属性。
   
    ![身份验证类型](./media/register-custom-api/authenticationtypes.png)
   
   * 将会根据 OpenAPI `securityDefinitions` 对象中的定义自动填充身份验证类型。 下面是一个 OAuth2.0 示例。
     
       ```
       "securityDefinitions": {
           "AAD": {
           "type": "oauth2",
           "flow": "accessCode",
           "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
           "tokenUrl": "https://login.windows.net/common/oauth2/token"
           "scopes": {}
           }
       },
       ```
   * 如果 OpenAPI 文件未使用 `securityDefintions` 对象，则不需要其他值。
   * 如果使用 Postman Collection，则仅当使用的身份验证类型受支持时（例如使用的是 OAuth 2.0 版或基本版），才会自动填充身份验证类型。
   * 如需设置 Azure Active Directory (AAD) 身份验证的示例，请参阅[创建适用于 Microsoft Flow 的自定义 Web API](customapi-web-api-tutorial.md#set-up-azure-active-directory-authentication)。
5. 系统会在“定义”选项卡中自动填充在 OpenAPI 文件或 Postman Collection 中定义的所有操作，以及请求和响应值。 如果所有必需的操作都已定义，则可转到注册过程的步骤 6，不需在此屏幕上进行更改。
   
    ![“定义”选项卡](./media/register-custom-api/definitiontab.png)
   
    若需编辑现有操作或向自定义连接器添加新操作，请继续阅读以下内容。
   
   1. 若需添加尚不在 OpenAPI 文件或 Postman Collection 中的新操作，请在左窗格中选择“新建操作”，然后在“常规”部分填写操作的名称、说明和可见性。
   2. 在“请求”部分的右上角选择“从示例导入”。 在右侧窗体中，粘贴一个示例请求。 API 文档通常会提供示例请求，你可以在该文档中获取填充“谓词”、“请求 URL”、“标头”和“正文”字段所需的信息。 如需示例，请参阅[文本分析 API 文档](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/operations/56f30ceeeda5650db055a3c6)。
      
      > [!IMPORTANT]
      > 请确保从操作中删除 `Content-type` 标头，因为 Microsoft Flow 会自动添加该标头。 已经在 Security 节中定义的身份验证标头也应从操作和触发器中删除。 
      > 
      > 
      
      ![从示例导入](./media/register-custom-api/importfromsample.png)
   3. 选择“导入”完成请求定义。 以类似方式定义响应。
6. 定义所有操作以后，请选择“创建”创建自定义连接器。
7. 创建自定义连接器以后，请转到“测试”选项卡，对 API 中定义的操作进行测试。 选择一个连接，然后提供测试操作时所需的输入参数。
   
    ![测试自定义连接器](./media/register-custom-api/testcustomapi.png)
   
    如果调用成功，则会获得有效响应。
   
    ![测试连接器响应](./media/register-custom-api/testapiresponse.png)

### <a name="quota-and-throttling"></a>配额和限制
* 有关自定义连接器创建配额的详细信息，请参阅 [Microsoft Flow 定价](https://flow.microsoft.com/pricing/)页。 与你共享的自定义连接器不计入该配额。
* 对于在自定义连接器上建立的每个连接，用户每分钟最多可以发出 500 个请求。

## <a name="share-your-custom-connector"></a>共享自定义连接器
有了自定义连接器以后，即可将其与组织中的其他用户共享。 请注意，共享自定义连接器会造成他人依赖该连接器，而删除自定义连接器则会删除到该连接器的所有连接。 若需为组织外部的用户提供连接器，请参阅[在 Microsoft Flow 中认证自定义连接器概述](api-connector-overview.md)。

1. 在 [flow.microsoft.com](https://flow.microsoft.com) 的顶栏中，选择用于打开设置菜单的齿轮图标。 选择“自定义连接器”选项。
   
    ![新连接](./media/register-custom-api/managecustomapi.png)
2. 选择连接器的省略号 (**. . .**) 按钮，然后选择“查看属性”。  
   
    ![查看连接器属性](./media/register-custom-api/view-properties.png)
3. 选择“共享”，然后输入需要向其授予连接器访问权限的用户或组。  
   
    ![共享自定义连接器](./media/register-custom-api/sharecustomapi.png)
4. 选择“保存”。

## <a name="next-steps"></a>后续步骤
[了解如何创建 Postman Collection](postman-collection.md)

[了解自定义 OpenAPI 扩展](customapi-how-to-swagger.md)。

[使用 ASP.NET Web API](customapi-web-api-tutorial.md)。

[注册 Azure 资源管理器 API](customapi-azure-resource-manager-tutorial.md)。

