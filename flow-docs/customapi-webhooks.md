---
title: "将 webhook 与 Microsoft Flow 配合使用 | Microsoft Docs"
description: "了解如何在 Microsoft Flow 中创建与 Webhook 交互的流"
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
ms.date: 05/08/2017
ms.author: deonhe
ms.openlocfilehash: cf899063ed6244e85d7eb0759efc9421cbdaa327
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="use-webhooks-with-microsoft-flow"></a>将 Webhook 与 Microsoft Flow 配合使用
[Webhook](http://www.webhooks.org/) 是用于提供事件通知的简单 HTTP 回调。  Microsoft Flow 允许使用 Webhook 来触发流。  本教程演示如何创建由 Webhook 触发的流。

> [!NOTE]
> 我们将使用 GitHub 作为可以通过 Webhook 发送通知的服务示例，但此处演示的方法可以扩展到任何使用 Webhook 的服务。
> 
> 

## <a name="prerequisites"></a>先决条件
若要完成本教程，你将需要：

* 基本了解 [Webhook](http://www.webhooks.org/)。
* 基本了解 [OpenAPI 规范](http://swagger.io/specification/) (Swagger)。
* [GitHub](https://www.github.com) 帐户。
* 用于本教程的[示例 OpenAPI JSON 文件](https://pwrappssamples.blob.core.windows.net/samples/githubWebhookSample.json)。
* 此外，如果不想手写 OpenAPI 文件，则也可使用[触发器 UI](customapi-webhooks.md#creating-webhook-triggers-from-the-ui) 来定义 Webhook 触发器。

## <a name="the-openapi-file"></a>OpenAPI 文件
Webhook 在 Microsoft Flow 中是作为一种[自定义连接器](register-custom-api.md)实现的，因此我们需要提供一个 OpenAPI JSON 文件以定义 Webhook 的形状。  OpenAPI 包含三个定义，这些定义对于 Webhook 正常工作至关重要：

1. 创建 Webhook
2. 定义来自 API（在此处为 GitHub）的传入挂钩请求
3. 删除 Webhook

### <a name="creating-the-webhook"></a>创建 Webhook
Webhook 在 GitHub 端根据 HTTP POST 创建到 `/repos/{owner}/{repo}/hooks`。  当使用 OpenAPI 中定义的触发器创建新流时，或者每当修改触发器时，Microsoft Flow 就需要将内容发布到此 URL。  在下面的示例中，`post` 属性包含将发布到 GitHub 的请求的架构。

```json
"/repos/{owner}/{repo}/hooks": {
    "x-ms-notification-content": {
    "description": "Details for Webhook",
    "schema": {
        "$ref": "#/definitions/WebhookPushResponse"
    }
    },
    "post": {
    "description": "Creates a Github webhook",
    "summary": "Triggers when a PUSH event occurs",
    "operationId": "webhook-trigger",
    "x-ms-trigger": "single",
    "parameters": [
        {
        "name": "owner",
        "in": "path",
        "description": "Name of the owner of targetted repository",
        "required": true,
        "type": "string"
        },
        {
        "name": "repo",
        "in": "path",
        "description": "Name of the repository",
        "required": true,
        "type": "string"
        },
        {
        "name": "Request body of webhook",
        "in": "body",
        "description": "This is the request body of the Webhook",
        "schema": {
            "$ref": "#/definitions/WebhookRequestBody"
        }
        }
    ],
    "responses": {
        "201": {
        "description": "Created",
        "schema": {
            "$ref": "#/definitions/WebhookCreationResponse"
        }
        }
    }
    }
},
```

> [!IMPORTANT]
> `"x-ms-trigger": "single"` 属性是一种架构扩展，它告诉 Microsoft Flow 将此 Webhook 显示在流设计器的可用触发器列表中，因此请确保包括它。
> 
> 

### <a name="defining-the-incoming-hook-request-from-the-api"></a>定义来自 API 的传入挂钩请求
传入挂钩请求（从 GitHub 到 Microsoft Flow 的通知）的形状是在自定义 `x-ms-notification-content` 属性中定义的，如以上示例所示。  它不需要包含请求的整个内容，只需包含你需要在流中使用的部分即可。

### <a name="deleting-the-webhook"></a>删除 Webhook
在 OpenAPI 中包括一个定义以便告诉 Microsoft Flow 如何删除 Webhook，是十分重要的。  每当你在流中更新触发器时，或者在你删除流时，Microsoft Flow 都会尝试删除 Webhook。

```json
"/repos/{owner}/{repo}/hooks/{hook_Id}": {
    "delete": {
    "description": "Deletes a Github webhook",
    "operationId": "DeleteTrigger",
    "parameters": [
        {
        "name": "owner",
        "in": "path",
        "description": "Name of the owner of targetted repository",
        "required": true,
        "type": "string"
        },
        {
        "name": "repo",
        "in": "path",
        "description": "Name of the repository",
        "required": true,
        "type": "string"
        },
        {
        "name": "hook_Id",
        "in": "path",
        "description": "ID of the Hook being deleted",
        "required": true,
        "type": "string"
        }
    ]
    }
},
```

> [!IMPORTANT]
> 为了使 Microsoft Flow 可以删除 Webhook，在创建 Webhook 时，API **必须**在 201 响应中包括 `Location` HTTP 标头。  `Location` 标头应包含将与 HTTP DELETE 一起使用的 Webhook 的路径。  例如，GitHub 的响应附带的 `Location` 遵循以下格式：`https://api.github.com/repos/<user name>/<repo name>/hooks/<hook ID>`。
> 
> 

## <a name="authentication"></a>身份验证
将 Webhook 请求发送到 Microsoft Flow 的 API 通常会采用某种形式的身份验证，GitHub 也不例外。  有几种类型的身份验证受支持。  对于本教程，我们将使用 GitHub 的个人访问令牌。

1. 导航到 [GitHub](https://www.github.com) 并登录（如果尚未执行该操作）。
2. 在右上角单击你的**个人资料图片**，然后在菜单中单击“设置”。
   
    ![设置](./media/customapi-webhooks/github-settings.png)
3. 在左侧菜单中的“开发人员设置”下，单击“个人访问令牌”。
   
    ![个人访问令牌](./media/customapi-webhooks/personal-access-tokens.png)
4. 单击“生成新令牌”按钮。
   
    ![生成新令牌](./media/customapi-webhooks/generate-new-token.png)
5. 在“令牌说明”框中，输入说明。
6. 选中 **admin:repo_hook** 复选框。
   
    ![admin:repo_hook](./media/customapi-webhooks/repo-hook.png)
7. 单击“生成令牌”按钮。
8. 记下你的新令牌。
   
    ![新令牌](./media/customapi-webhooks/new-token.png)
   
   > [!IMPORTANT]
   > 你将无法再次访问此令牌。 应将其复制并粘贴到某个位置（如记事本），以便稍后在本教程中使用。
   > 
   > 

## <a name="adding-the-webhook-to-microsoft-flow"></a>向 Microsoft Flow 添加 Webhook
现在已具备将 Webhook 作为自定义连接器添加到 Microsoft Flow 的一切条件。

1. 导航到 [Microsoft Flow Web 门户](https://flow.microsoft.com)并登录（如果尚未执行此操作）。
2. 单击“设置”图标，然后单击“自定义连接器”。
   
    ![自定义连接器](./media/customapi-webhooks/custom-apis.png)
3. 单击“创建自定义连接器”按钮。
4. 单击“导入 OpenAPI”框中的文件夹图标，然后选择示例 OpenAPI 文件。
5. 单击“常规信息”部分中的“上载”图标，然后选择要用作图标的图像文件。
6. 单击“继续”。
   
    ![导入 OpenAPI](./media/customapi-webhooks/import-swagger.png)
7. 在下一个屏幕中，我们将配置安全设置。  在“身份验证类型”下，选择“基本身份验证”。
8. 在“基本身份验证”部分中，为标签字段输入文本“用户名”和“密码”。  请注意，这些是仅当在流中使用该触发器时才显示的标签。
   
    ![基本身份验证](./media/customapi-webhooks/basic-auth.png)
9. 在页面顶部，为流提供名称并单击“创建连接器”。
   
    ![创建 API](./media/customapi-webhooks/create-api.png)

新的自定义连接器现在应出现在自定义连接器页面的列表中。

## <a name="creating-webhook-triggers-from-the-ui"></a>从 UI 创建 Webhook 触发器
1. 上传/创建基线 OpenAPI 文件以后，请导航到自定义连接器向导的“定义”选项卡。
2. 在左侧窗格中单击“+ 新建触发器”，填写触发器的说明。 在此示例中，我们将创建一个触发器，一向存储库发出拉取请求就会触发该触发器。
   
    ![创建触发器 1](./media/customapi-webhooks/create-new-trigger-1.png)
3. 接下来，定义创建 Webhook 触发器的请求。 为此，可以导入一个示例性的 *Webhook 触发器创建*请求。 请查看 [Github API 参考](https://developer.github.com/v3/repos/hooks/#create-a-hook)，了解如何创建 Webhook。 
4. Microsoft Flow 自动添加标准的 ```content-type``` 和安全性标头，因此在从示例导入时，不需定义这些标头。 
   
    ![创建触发器 2](./media/customapi-webhooks/create-new-trigger-2.png)
5. 导入“创建 Webhook”请求后，接下来将定义 Webhook 响应，只需从示例响应导入即可。 请查看 [Github API 参考](https://developer.github.com/v3/activity/events/types/#pullrequestevent)，了解拉取请求事件。 
   
    **注意**：无需粘贴完整的响应。 只应定义所需字段。
   就此示例来说，我们仅提取 PR URL 以及发出 PR 的用户的信息。
   
    ![创建触发器 3](./media/customapi-webhooks/create-new-trigger-3.png)
6. 最后一步是选择 Webhook 创建请求中的参数，Microsoft Flow 会在该参数的值中填充一个供 Github 填充的回调 URL。 对于我们来说，这就是 ```config``` 对象中的 URL 属性。
   
    ![创建触发器 4](./media/customapi-webhooks/create-new-trigger-4.png)

## <a name="using-the-webhook-as-a-trigger"></a>使用 Webhook 作为触发器
现在，我们已配置好了所有内容，我们可以在流中使用 Webhook 了。  让我们创建一个流，每当 GitHub 存储库收到 git 推送时，该流就会向 Microsoft Flow 移动应用发送推送通知。

1. 在 [Microsoft Flow Web 门户](https://flow.microsoft.com)中的页面顶部，单击“我的流”。
2. 单击“从空白创建”。
3. 在适用于 Microsoft Flow 的设计器中，搜索以前注册的自定义连接器。
   
    ![新触发器](./media/customapi-webhooks/new-trigger.png)
   
    在列表中单击该项目以将其用作触发器。
4. 由于这是我们首次使用此自定义连接器，我们必须连接到它。  对于**连接名称**，请输入描述性名称。  对于 **用户名**，请使用你的 GitHub 用户名。  对于**密码**，请使用你以前创建的**个人访问令牌**。
   
    ![新连接](./media/customapi-webhooks/new-connection.png)
   
    单击“创建”。
5. 现在，我们需要向 Microsoft Flow 提供要监视的存储库的相关信息。  可以识别 OpenAPI 文件中 **WebhookRequestBody** 对象提供的字段。  对于**所有者**和**存储库**，请输入你想要监视的 GitHub 存储库的所有者和存储库名称。
   
    ![存储库信息](./media/customapi-webhooks/repo-info.png)
   
   > [!IMPORTANT]
   > 在此示例中，我正在使用 [Visual Studio Code](https://code.visualstudio.com) 的存储库。 你应使用你的帐户有权访问的存储库。  做到这一点的最简单方法是使用你自己的存储库。
   > 
   > 
6. 单击“+ 新建步骤”，然后单击“添加操作”。
7. 搜索并选择“推送通知”操作。
   
    ![推送通知](./media/customapi-webhooks/push-notification.png)
8. 在“文本”字段中输入一些文本。  请注意，OpenAPI 文件中的 **WebhookPushResponse** 对象定义你可以使用的一组参数。
   
    ![推送通知详细信息](./media/customapi-webhooks/push-details.png)
9. 在页面顶部，为流提供名称并单击“创建流”。
   
    ![流名称](./media/customapi-webhooks/flow-name.png)

## <a name="verification-and-troubleshooting"></a>验证和故障排除
若要验证是否所有内容均已正确设置，请单击“我的流”，然后单击此新流旁边的“信息”图标，查看运行历史记录。  你应已从 Webhook 创建过程中至少看到一个“已成功”运行。  这表示已在 GitHub 端成功创建了 Webhook。  如果运行失败，可以钻取到运行详细信息，查看失败的原因。  如果是由于“404 未找到”响应而导致失败，那么你的 GitHub 帐户很可能没有正确的权限，无法在你使用的存储库上创建 Webhook。

## <a name="summary"></a>摘要
如果所有内容均已正确配置，那么现在每当所选 GitHub 存储库上发生 git push 时，你都将在 Microsoft Flow 移动应用中收到推送通知。  执行上述过程，你便可以在流中使用任何支持 Webhook 的服务作为触发器。

## <a name="next-steps"></a>后续步骤
* [注册自定义连接器](register-custom-api.md)。
* [使用 ASP.NET Web API](customapi-web-api-tutorial.md)。
* [注册 Azure 资源管理器 API](customapi-azure-resource-manager-tutorial.md)。

