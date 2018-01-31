---
title: "Microsoft Flow 中适用于自定义连接器的 OpenAPI 扩展 | Microsoft Docs"
description: "查看 OpenAPI 与 Microsoft Flow 配合使用时所需的架构扩展"
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: sunaysv
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: sunayv
ms.openlocfilehash: b8fdc04c16701c876d84e9761a48093fa5fb195c
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2018
---
# <a name="openapi-extensions-for-custom-connectors-in-microsoft-flow"></a>Microsoft Flow 中适用于自定义连接器的 OpenAPI 扩展
## <a name="introduction"></a>简介
若要为 Microsoft Flow、Azure 逻辑应用或 Microsoft PowerApps 创建自定义连接器，必须提供 OpenAPI 定义文件，它是与语言无关的机器可读文档，用于描述 API 的操作和参数。 配合 OpenAPI 的现成可用的功能，在为逻辑应用和流创建自定义连接器时，还可以包含这些 OpenAPI 扩展：

* `summary`
* `x-ms-summary`
* `description`
* `x-ms-visibility`
* `x-ms-dynamic-values`
* `x-ms-dynamic-schema`

以下是关于这些扩展的更多详细信息：

<a name="summary"></a>

## <a name="summary"></a>摘要
指定操作的标题。 </br>
适用于：操作 </br>
建议：为 `summary` 使用*句子首字母大写*。 </br>
示例：“When an event is added to calendar”或“Send an email”

![每个操作的“summary”](./media/custom-connector-openapi-extensions/summary.png)

``` json
"actions" {
  "Send_an_email": {
    /// Other action properties here...
    "summary": "Send an email",
    /// Other action properties here...
  }
},
```

## <a name="x-ms-summary"></a>x-ms-summary
指定实体的标题。 </br>
适用于：参数、响应架构 </br>
建议：为 `x-ms-summary` 使用*单词首字母大写*。 </br>
示例：“Calendar ID”、“Subject”、“Event Description”等

![每个实体的“x-ms-summary”](./media/custom-connector-openapi-extensions/x-ms-summary.png)

``` json
"actions" {
  "Send_an_email": {
    /// Other action properties here...
    "parameters": [ 
      {
        /// Other parameters here...
        "x-ms-summary": "Subject",
        /// Other parameters here...
      }
    ]
  }
},
```
<a name="description"></a>

## <a name="description"></a>说明
指定有关操作的功能或实体的格式和函数的详细说明。 </br>
适用于：操作、参数、响应架构 </br>
建议：为 `description` 使用*句子首字母大写*。 </br>
示例：“This operation triggers when a new event is added to the calendar”、“Specify the subject of the mail.”等

![每个操作或实体的“description”](./media/custom-connector-openapi-extensions/description.png)

``` json
"actions" {
  "Send_an_email": {
     "description": "Specify the subject of the mail",
     /// Other action properties here...
  }
},
```

<a name="visibility"></a>

## <a name="x-ms-visibility"></a>x-ms-visibility
指定面向用户的实体可见性。 </br>
可能的值：`important`、`advanced` 和 `internal` </br>
适用于：操作、参数、架构

* `important` 操作和参数始终首先向用户显示。
* `advanced` 操作和参数隐藏在其他菜单下。
* `internal` 操作和参数向用户隐藏。

> [!NOTE]
> 对于 `internal` 和 `required` 的参数，**必须**为这些参数提供默认值。
> 
> 

示例：“查看更多”菜单和“显示高级选项”菜单隐藏 `advanced` 操作和参数。

![用于显示或隐藏操作和参数的“x-ms-visibility”](./media/custom-connector-openapi-extensions/x-ms-visibility.png)

``` json
"actions" {
  "Send_an_email": {
     /// Other action properties here...
     "parameters:": [
         {
           "name": "Subject",
           "type": "string",
           "description": "Specify the subject of the mail",
           "x-ms-summary": "Subject",
           "x-ms-visibility": "important",
           /// Other parameter properties here
         }
     ]
     /// Other action properties here...
  }
},
```

## <a name="x-ms-dynamic-values"></a>x-ms-dynamic-values
为用户显示填充的列表，以便他们可以为操作选择输入参数。 </br>
适用于：参数 </br>
如何使用：将 `x-ms-dynamic-values` 对象添加到参数的定义。 例如，请参阅此 [OpenAPI 示例](https://procsi.blob.core.windows.net/blog-images/sampleDynamicSwagger.json)。

![用于显示列表的“x-ms-dynamic-values”](./media/custom-connector-openapi-extensions/x-ms-dynamic-values.png)

### <a name="properties-for-x-ms-dynamic-values"></a>x-ms-dynamic-values 的属性
| 名称 | 必需或可选 | 说明 |
| --- | --- | --- |
| **operationID** |必需 |调用用于填充列表的操作。 |
| **value-path** |必需 |`value-collection` 内的对象中引用参数值的路径字符串。 如果未指定 `value-collection`，响应将评估为数组。 |
| **value-title** |可选 |`value-collection` 内的对象中引用值说明的路径字符串。 如果未指定 `value-collection`，响应将评估为数组。 |
| **value-collection** |可选 |计算结果为响应有效负载中的对象数组的路径字符串 |
| **parameters** |可选 |一个对象，其属性指定调用动态值操作所必需的输入参数 |

下面是演示 `x-ms-dynamic-values` 中的属性的示例：

``` json
"x-ms-dynamic-values": {
  "operationId": "PopulateDropdown",
  "value-path": "name",
  "value-title": "properties/displayName",
  "value-collection": "value",
  "parameters": {
     "staticParameter": "{value}",
     "dynamicParameter": {
        "parameter": "{value-to-pass-to-dynamicParameter}"
     }
  }
}
```

## <a name="example-all-the-openapi-extensions-up-to-this-point"></a>示例：到目前为止的所有 OpenAPI 扩展
``` json
"/api/lists/{listID-dynamic}": {
    "get": {
        "description": "Get items from a single list - uses dynamic values and outputs dynamic schema",
        "summary": "Gets items from the selected list",
        "operationID": "GetListItems",
        "parameters": [
           {
             "name": "listID-dynamic",
             "type": "string",
             "in": "path",
             "description": "Select the list from where you want outputs",
             "required": true,
             "x-ms-summary": "Select List",
             "x-ms-dynamic-values": {
                "operationID": "GetLists",
                "value-path": "id",
                "value-title": "name"
             }
           }
        ]
    }
}
```

## <a name="x-ms-dynamic-schema"></a>x-ms-dynamic-schema
指示当前参数或响应的架构为动态。 此对象可调用由此字段的值定义的操作，动态发现架构，并显示用于收集用户输入的适当 UI 或显示可用字段。 

适用于：参数、响应

如何使用：将 `x-ms-dynamic-schema` 对象添加到请求参数或响应正文定义。 例如，请参阅此 [OpenAPI 示例](https://procsi.blob.core.windows.net/blog-images/sampleDynamicSwagger.json)。

此示例演示输入窗体如何基于用户从下拉列表中选择的项目而变化：

![动态参数的“x-ms-dynamic-schema”](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema.png)

此示例演示输出如何基于用户从下拉列表中选择的项目而变化。 在此版本中，用户选择“汽车”：

![用于选择项目“汽车”的“x-ms-dynamic-schema-response”](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema-output1.png)

在此版本中，用户选择“食物”：

![用于选择项目“食物”的“x-ms-dynamic-schema-response”](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema-output2.png)

### <a name="properties-for-x-ms-dynamic-schema"></a>x-ms-dynamic-schema 的属性
| 名称 | 必需或可选 | 说明 |
| --- | --- | --- |
| **operationID** |必需 |调用用于提取架构的操作 |
| **parameters** |必需 |一个对象，其属性指定调用动态架构操作所必需的输入参数 |
| **value-path** |可选 |引用具有该架构的属性的路径字符串。 </br>如果未指定，响应应在根对象的属性中包含该架构。 |
|  | | |

下面是动态参数的示例：

``` json
{
  "name": "dynamicListSchema",
  "in": "body",
  "description": "Dynamic schema for items in the selected list",
  "schema": {
    "type": "object",
    "x-ms-dynamic-schema": {
        "operationID": "GetListSchema",
        "parameters": {
          "listID": {
            "parameter": "listID-dynamic"
          }
        },
        "value-path": "items"
    }
  }
}
```

下面是动态响应的示例：

``` json
"DynamicResponseGetListSchema": {
   "type": "object",
   "x-ms-dynamic-schema": {
      "operationID": "GetListSchema",
      "parameters": {
         "listID": {
            "parameter": "listID-dynamic"
         }
      },
      "value-path": "items"
    }
}
```

## <a name="next-steps"></a>后续步骤
[注册自定义连接器](register-custom-api.md)。

[使用 ASP.NET Web API](customapi-web-api-tutorial.md)。

[注册 Azure 资源管理器 API](customapi-azure-resource-manager-tutorial.md)。

