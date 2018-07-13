---
title: 使用 Markdown 格式化 Microsoft Flow 审批 | Microsoft Docs
description: 了解如何使用 Markdown 来格式化 Microsoft Flow 审批请求。
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
ms.openlocfilehash: dc8d9d650b02b7962770ff0574deb151492739d9
ms.sourcegitcommit: 4a8d11e1768cd0ca96a60b6f5548a68c0c8999e5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2018
ms.locfileid: "32323623"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>在 Microsoft Flow 审批请求中使用 Markdown

本文介绍如何使用 [Markdown](https://en.wikipedia.org/wiki/Markdown) 语法向审批请求添加丰富的格式和表。

## <a name="headers"></a>标头

使用标头构造注释。 标头可分割较长注释，使它们更易于阅读。

以哈希字符 `#` 作为行的开头来设置标题。 通过使用其他哈希字符（例如 `####`）作为行的开头来组织带副标题的注解。 支持最多六个级别的标题。

示例：

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

结果：

![导出流](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>段落和换行符

通过段落或换行符进行分段，使文本更易于阅读。 在换行符前输入两个空格开始一个新段落，或者连续输入两个换行符开始一个新段落。   
   
示例

<pre>
Add lines between your text with the Enter key.
This spaces your text better and makes it easier to read.
</pre>

结果：   
在文本与 Enter 键之间添加行。      
这可以更好地将文本隔开，并使其更易于阅读。


示例 2

<pre>
Add two spaces prior to the end of the line.(space, space)     
This adds space in between paragraphs.
</pre>

结果：  
在行结束前添加两个空格。   

这将在段落之间添加空格。
  

## <a name="lists"></a>列表

使用列表组织相关项。 可以为排序列表添加编号，或者为未排序的列表仅添加项目符号。

排序列表以数字开头，后跟每个列表项和句号。 未排序的列表以 `*` 开头。 在新行上开始每个列表项。 在 Markdown 文件 或小组件中，在换行符前输入两个空格开始一个新段落，或者连续输入两个换行符开始一个新段落。   

### <a name="ordered-or-numbered-lists"></a>排序或编号列表

示例：

```Markdown
0. First item.
0. Second item.
0. Third item.
```

结果：

1. 第一项。
2. 第二项。
3. 第三项。

### <a name="bullet-lists"></a>项目符号列表

示例：

<pre>

- Item 1
- Item 2
- Item 3

</pre>

结果：

- 项目 1
- 项目 2
- 项目 3

### <a name="nested-lists"></a>嵌套列表

示例：
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

结果：  

1. 第一项。

    - 项目 1
    - 项目 2
    - 项目 3
2. 第二项。
    - 嵌套项 1
    - 嵌套项 2
    - 嵌套项 3


## <a name="links"></a>链接

自动将 HTTP 和 HTTPS URL 的格式设置为链接。 

可以使用标准的 Markdown 链接语法为 URL 设置文本超链接：

```Markdown
[Link Text](Link URL)
```

示例：
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

结果：

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>定位标记链接

当以 HTML 格式呈现时，定位标记 ID 将分配给所有标题。 该 ID 为标题文本，空格替换为短划线 (-) 且字母全小写。

示例：

<pre>
###Link to a heading in the page
</pre>

<br/>

结果：

到某部分的定位标记链接的语法...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
该 ID 全部小写，且链接区分大小写，因此请确保使用小写，即使标题本身使用大写形式。


## <a name="tables"></a>表

使用表组织结构化的数据。 

- 将每个表行放在其自己的行上 
- 使用竖线 `|` 分隔表单元格 
- 表的前两行在表中设置列标头和元素的对齐方式
- 在划分表的标头和正文时，使用冒号 (`:`) 来指定列的对齐方式（左对齐、居中、右对齐） 
- 若要开始新行，使用 HTML 换行符标记 (`<br/>`)（在 Wiki 中有效，在其他位置无效）  
- 请确保以 CR 或 LF 结束每一行。 

示例：

<pre>
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
</pre>  <br/>

结果：  

| 标题 1 | 标题 2 | 标题 3 |  
|-----------|:---------:|-----------:|  
| 单元格 A1 | 单元格 A2 | 单元格 A3 |  
| 单元格 B1 | 单元格 B2 | 单元格 B3<br/>第二行文本 |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>强调（粗体、斜体、删除线）  

可以通过对字符应用粗体、斜体或删除线来强调文本： 
- 要应用斜体：将文本括在星号 `*` 或下划线 `_` 中   
- 要应用粗体：将文本括在双星号 `**` 中。    
- 要应用删除线：将文本括在双波浪号 `~~` 中。   

结合这些元素对文本应用多个强调效果。    

示例：

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

结果：

在注释中使用强调来表示强烈的意见并指出<s>更正</s>   
粗体、斜体文本   
~~粗体、带删除线的文本~~  


## <a name="special-characters"></a>特殊字符

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">语法</th>
<th width="350px">示例/说明</th>
</tr>



<tr>
<td>
<p>若要插入以下字符之一，请添加反斜杠前缀：</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>有关插入特殊字符的一些示例
<p>输入 ```\\``` 获取 \\ </p>
<p>输入 ```\_``` 获取 _ </p>
<p>输入 ```\#``` 获取 \# </p>
<p>输入 ```\(``` 获取 \( </p>
<p>输入 ```\.``` 获取 \. </p>
<p>输入 ```\!``` 获取 \! </p>
</td>
</tr>

</tbody>
</table>
