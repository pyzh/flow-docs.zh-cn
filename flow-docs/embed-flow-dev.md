---
title: 将 Microsoft Flow 与网站和应用集成 | Microsoft Docs
description: 将 Microsoft Flow 体验嵌入网站或应用中。
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: barathb
ms.openlocfilehash: af03ee70b09ba5ee1164a9a7ea5019b13c19eec6
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440039"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>将 Microsoft Flow 与网站和应用集成
将 Microsoft Flow 直接嵌入应用或网站中，方便用户自动完成其个人任务或专业任务。

若要创建流，用户需提供 **Microsoft 帐户**或 **Azure Active Directory** 中的工作帐户或学校帐户。 Microsoft Flow 不支持某些功能，例如，不支持白标解决方案，此类方案支持系统所使用的任何标识（除非 Microsoft Flow 已使用 Microsoft 帐户或 AAD）。

## <a name="prerequisites"></a>先决条件
* [生成自定义连接器](register-custom-api.md)：将服务连接到 Microsoft Flow。
* [创建和发布一个或多个模板](publish-a-template.md)：使用用户的 API。

## <a name="show-templates-for-your-scenarios"></a>显示适合用户方案的模板
开始时请添加以下代码，直接在网站中显示流模板：

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**注意**：我们添加了一个分行符，改进代码在页面上的显示效果。

| 参数 | 说明 |
| --- | --- |
| 区域设置 |模板视图的四字母语言和区域代码。 例如，`en-us` 代表美式英语，`de-de` 代表德语。 |
| 搜索词 |要在视图中显示的模板的搜索词。 例如，搜索 `wunderlist` 即可显示 Wunderlist 模板。 |
| 模板数 |要在视图中显示的模板的数量。 |
| 目标 |当用户单击模板时打开的页面。 指定 `details` 即可显示模板详细信息，指定 `new` 即可打开 Microsoft Flow 设计器。 |
| parameters.{name} |要传递到流中的其他上下文。 |

如果目标参数为 `new`，则 Microsoft Flow 会在用户单击模板时打开，用户可以在设计器中创建流。 若要在应用内获得完全的体验，请参阅下一部分。

### <a name="passing-additional-parameters-to-the-flow"></a>将附加参数传递到流
如果用户位于网站或应用的特定上下文中，则可能需要将该上下文传递到流。 例如，用户可能会在 Wunderlist 中查看特定列表时打开一个模板，该模板的功能是“项目添加到列表中时通知我”。 执行以下步骤即可将列表 ID 以参数形式传递到流：

1. 在发布参数之前在流模板中定义参数。 参数如下所示：`@{parameters('parameter_name')}`。
2. 在 iframe src 中传递参数。例如，如果有一个名为 **listName** 的参数，则可添加 `&parameters.listName={the name of the list}`。

### <a name="full-sample"></a>完整示例
若要以德语形式显示有关 Wunderlist 的四大模板并通过 **myCoolList** 启动用户，请执行以下操作：

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>嵌入流管理
使用经过身份验证的 Flow SDK，让用户直接通过网站或应用创建和管理流（不需导航到 Microsoft Flow 门户）。 用户需登录到 Microsoft 帐户或 Azure Active Directory 才能使用经过身份验证的 SDK。

> [!NOTE]
> 在你的应用程序中使用 Microsoft Flow 的所有用户都将是 Microsoft Flow 用户。 无法隐藏 Microsoft Flow 品牌。
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>包括 JavaScript，适用于经过身份验证的 SDK
遵照此示例在 HTML 代码中包括 SDK。 也可下载、缩小 SDK 并将其与产品打包在一起。

```javascript
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>创建一个用于容纳视图的容器
添加 HTML div：

```html
<div id="flowDiv" class="flowContainer"></div>
```

建议对此容器进行样式化处理，使之在使用时显示适当的维度：

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

请注意，iframe 在宽度低于 320 像素时无法正常呈现，在宽度超出 1200 像素时无法填充内容。 任何高度均可。

### <a name="authentication-against-the-sdk"></a>针对 SDK 进行身份验证
若要列出用户已创作的流并通过模板创建流，请提供源自 AAD 的 authToken。

```javascript
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https:/flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv'
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

若要查找 `environmentId`，可以进行下述 API 调用，以便返回可供用户访问的环境的列表：

```http
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

这样会返回一个带环境列表的 JSON 响应，你可以从该列表中选取任何环境。 查看属性 `properties.isDefault=true` 即可查找默认的用户环境。

在此示例中，`requestParam` 定义为：

```javascript
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

接下来需要注意的是，`widgetDoneCallback` 是一个回调函数，需在主机获得令牌后进行调用。 这样做是因为获得令牌可能是一个异步过程。 调用此函数时需传入的参数为 `(errorResult: any, successResult: any)`。 successResult 将取决于回调类型。 `GetAccessToken` 的类型为：

```javascript
export interface IGetAccessTokenResult {
    token: string;
}
```
