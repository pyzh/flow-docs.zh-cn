---
title: 发行说明 | Microsoft Docs
description: 常见问题以及 Microsoft Flow 版本的新增功能
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/12/2018
ms.author: stepsic
ms.openlocfilehash: ef14fd29dbf0b227acf4d5fef6233837514d4ab0
ms.sourcegitcommit: d00c10759d4afb54517a0b1032f8d0a509006d5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="release-notes"></a>发行说明
## <a name="top-questions"></a>最常见的问题
1. 流发生故障。 如何修复？
   
   1. 确定故障。 这可以通过访问 Web 门户顶部的通知图标，或在移动应用中选择“活动”选项卡来开始。 应当可以在那里看到你的流，并且可以选择它。
   2. 现在可以查看流详细信息。 查找带红色感叹号图标的步骤，在那里会看到流的错误消息。
   3. 根据错误消息，应该能够**编辑**流并修复它。 [阅读有关如何修复常见流故障的详细信息](fix-flow-failures.md)。
2. 如何使用高级条件或表达式？
   
   * 了解如何[添加条件](add-condition.md)。
   * 若要在流中设置多种情况，请单击或点击“添加条件”，在现有条件中添加条件。
   * 通过引用[逻辑应用中的函数](https://docs.microsoft.com/rest/api/logic/definition-language)创建高级表达式。
3. 授权是怎样与 Office 365 配合工作的？
   
   * 如果你是 Office 365 用户，则可通过适用于 Office 365 的 Microsoft Flow 计划获取完全访问权限。 有关详细信息，请参阅 [Microsoft Flow 定价计划](https://flow.microsoft.com/pricing/)。
   * 如果你是管理员，则可查看有关 [Microsoft Flow 许可](organization-q-and-a.md)的信息，包括使用 Office 365 时的相关许可信息。

## <a name="known-issues-and-resolutions"></a>常见问题和解决方法
1. 不支持“我的站点”中非“自定义列表”类型的 SharePoint 列表。  若要解决此问题，请在标准 SharePoint 站点中创建自定义列表。
2. 可以将流写入 SharePoint 列表中的分类字段。 建议使用简单的字符串字段，直至此问题得到更正。
3. 向所选文件夹中的嵌套文件夹添加文件时，不会触发文件触发器。

## <a name="whats-new"></a>新增功能

### <a name="release-2018-04-12"></a>2018 年 4 月 12 日版

- **将数据从流返回到 PowerApps** - 生成可从使用 PowerApps 生成的应用中调用的流，并将数据返回到应用。 使用可视化拖放流设计器生成应用所需的逻辑。 
- **将多条记录添加到数组输入** - 例如，将列表生成器添加到了 Microsoft Flow，可用于将多个附件添加到电子邮件。
- **使用先前运行的数据来测试流** - 在设计器中添加了一个新的“测试流”按钮，以便用户可以使用之前流运行的触发器数据来测试流。
- **新的 workflow() 字段** - 现可使用 workflow() 表达式访问环境名称和流显示名称。

[阅读更多并询问](https://flow.microsoft.com/blog/return-data-to-powerapps/)有关此版本的问题。

### <a name="release-2018-04-04"></a>2018 年 4 月 4 日版

- **Common Data Service 的审批** - 新式审批构建在应用的 Common Data Service 最新版本之上。 这意味着你可生成能够读取使用 CDS 连接器发送或接收的审批状态的流。
- **查找应用到每项的错误** - 即使循环中有数百个项，也可在流运行视图中直接跳转到循环错误。
- **重新分配审批** - 可将收到的任何审批分配给组织中的其他人，从而将审批委托给他们。 
- **会议室列表** - Office 365 Outlook 连接器添加了用于获取组织会议室数据的操作。
- **查看流按钮的详细信息** - 运行他人共享给你的流时，现可看到流使用的所有操作。
- **英国区域** - 现可创建环境，将其数据存储在英国。
- **两个新连接器** - 增加了对 AtBot Admin 和 Marketing Content Hub 的支持。
- **新的文档登陆页面** - 更新了文档登陆页面，便于将内容按用户身份分组：初学者、中级用户或专家。 

[阅读更多并询问](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/)有关此版本的问题。

### <a name="release-2018-03-13"></a>2018 年 3 月 13 日版

- **审批历史记录** - 查看发送的所有审批请求，包括回复、发送的评论以及发生的确切时间。
- **四个新连接器** - 添加了 Excel Online（商业版）、Excel Online (OneDrive)、Azure SQL 数据仓库和 Pitney Bowes 税款计算器。
- **动态内容工具提示** - 将鼠标悬停在动态内容上，可查看其动作内容的来源，并在不完全打开表达式编辑器的情况下预览表达式。
- **并发控制** - 启用并发控制，使给定流一次只能运行一个。
- **指数重试** - 一种新型的重试策略，使重试间隔随时间推移而呈指数级增长。
- **辅助功能一致性** - 发布了新的一致性文档，介绍 Microsoft Flow 如何满足辅助功能标准。

[阅读更多并询问](https://flow.microsoft.com/blog/approval-history-accessibility/)有关此版本的问题。

### <a name="release-2018-02-09"></a>2018 年 2 月 9 日版

- **网关高可用性** - 创建高度可用的本地数据网关群集，以便在单个计算机停机时保持连接。
- **改进的“应用到每个”** - 使用 Flow 计划 1 或 Flow 计划 2 可以在单次运行中处理多达 100,000 个项目，并在“应用到每个”循环中并行处理 50 个操作。 

[阅读更多并询问](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/)有关此版本的问题。

### <a name="release-2018-01-29"></a>2018 年 1 月 29 日版

- **Microsoft Teams 内部流** - 通过 Teams，可以创建和管理流、查看你接收和发送的批准，以及直接在 Teams 桌面应用内或在 teams.microsoft.com 上启动流 - [在此处了解详细信息](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/)。
- **共享编辑通知** - 每当有同事更改你所拥有的流时，你将会收到电子邮件通知，告知你谁更改了哪个流。
- **新表达式** - 添加了两组新的表达式：一组用于分析 URL，另一组用于与 JSON 对象结合使用。
- **三个新连接器** - 本周提供两个新的 Plumsail 连接器：Plumsail SP 和 Plumsail 窗体以及一个到 kintone 的新连接器。

[阅读更多并询问](https://flow.microsoft.com/blog/shared-notifications-and-expressions/)有关此版本的问题。

### <a name="release-2018-01-17"></a>2018 年 1 月 17 日版

- **Office 365 配置文件信息** - 我们已向 Office 365 Users 连接器添加了可与用户配置文件和照片结合使用的新操作。
- **追加到字符串变量** - 可以添加到循环内的字符串来构建表或其他列表。
- **Infobip 连接器** - Infobip 是一项服务，可实现企业级通信，包括语音呼叫，以及在入站 SMS 上触发。

[阅读更多并询问](https://flow.microsoft.com/blog/o365-profile-infobip/)有关此版本的问题。

### <a name="release-2017-12-20"></a>2017 年 12 月 20 日版

Microsoft Flow Analytics 现已在所有 Microsoft Flow 区域中推出，这意味着，我们可以更深入地洞察环境中的流的运行状况。

[阅读更多并询问](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/)有关此版本的问题。


### <a name="release-2017-12-14"></a>2017 年 12 月 14 日版

- **Outlook 连接器改进** - 可将电子邮件另存为“.eml”文件，自动响应日历邀请，以及根据电子邮件线索中的提醒触发流。
- **连接改进** - Microsoft Flow 会记住你最近使用的连接，并会显示所有新添加的连接器。
- **5 个新连接器** - 添加了 Azure 容器实例、Azure Kusto、Metatask、微软待办和 Plumsail 文档。
- **HTTP 改进** - HTTP 操作现在支持区块编码。

[阅读更多并询问](https://flow.microsoft.com/blog/outlook-connector-more/)有关此版本的问题。

### <a name="release-2017-12-05"></a>2017 年 12 月 5 日版

Microsoft Flow 启动面板现已在所有区域推出。 在 SharePoint 列表或文档库中运行某个流时，可以使用此面板将值添加到该流。

[阅读更多并询问](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/)有关此版本的问题。


### <a name="release-2017-11-28"></a>2017 年 11 月 28 日版

- **托管元数据** - 从 SharePoint 中使用托管元数据（也称为 分类）类型的列读取数据，以及向其中写入数据。
- **追加到数组** - 使用新的“追加到数组变量”操作将项添加到数组末尾。
- **Tago** - Tago 的新连接器，可将电子设备轻松连接到外部数据，以使用上下文分析促成更明智的决策。
- **iPhone X** - 在 iPhone X 上使用全屏幕的新版 Microsoft Flow 应用，对图像上传的速度做了改进。

[阅读更多并询问](https://flow.microsoft.com/blog/managed-metadata-tago/)有关此版本的问题。

### <a name="release-2017-11-09"></a>2017 年 11 月 9 日版

- **OneDrive for Business 集成** - [OneDrive for Business 中现在提供了一个流按钮](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/)，使用它可在选定的文件或文件夹中创建或触发流。
- **计划程序触发器** - 创建新任务、向你分配了任务或者完成了某个任务时启动流。
- **SharePoint 附件** - 处理 SharePoint 列表项中的附件：列出、下载、添加或删除附件。
- **流管理连接器** - 创建可以自动管理环境中其他流的流（例如，自动将权限添加到流）。
- **四个新连接器** - 添加了 Azure 自定义影像服务、D&B Optimizer、Enadoc 和 Derdak SIGNL4。 
- **更多连接器操作** - 运行 SQL 查询、获取更快的电子邮件触发器、在 Azure AD 中将任何方法与 HTTP 配合使用，等等。

[阅读更多并询问](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/)有关此版本的问题。

### <a name="release-2017-11-02"></a>2017 年 11 月 2 日版

- **审核日志记录** - Microsoft Flow 审核事件现已在所有租户的 Office 365 安全性和符合性中心推出。
- **Flow 小组件修复** - 修复了 Flow 移动应用中导致按钮无法在小组件中加载的问题。

[阅读更多并询问](https://flow.microsoft.com/blog/security-and-compliance-center/)有关此版本的问题。

### <a name="release-2017-10-19"></a>2017 年 10 月 19 日版

- **嵌套了“应用到每项”操作** - 可以添加“应用到每项”操作，以及在其他“应用到每项”容器操作中进行筛选和选择。
- **日期时间操作** - 添加了用于获取本地时间、时间相加、时间相减和设置时间格式的新操作。
- **四个新连接器** - 添加了内容审查器、Docparser、Microsoft Kaizala 和 Pitney Bowes 数据验证。
- **改进了连接体验** - 连接断开时，Flow 门户中会显示通知，此外还提供更丰富的连接详细信息。
- **出差模板集合** - 面向[出差工作人员](https://flow.microsoft.com/collections/onthego/)的新模板集合。
- **电子邮件地址按钮输入** - 当用户运行按钮时从用户收集电子邮件地址。
- **文件按钮输入** - 当用户运行按钮时，从用户获取上传的文件，例如照片。
- **首次运行和自动登录** - 改进了移动应用中的首次运行体验，包括自动登录。
- **更快的 Microsoft Forms 触发器** - Forms 触发流的速度比以往要快得多（以前为每小时触发一次）。
- **在不同的会话中保留按钮输入** - 在手机上触发的按钮会记住以前的输入。
- **移动活动源** - 改进了活动源，包含更详细的运行摘要和故障排除详细信息。

[阅读更多并询问](https://flow.microsoft.com/blog/nested-apply-to-each/)有关此版本的问题。

### <a name="release-2017-10-03"></a>2017 年 10 月 3 日版

- **必须全部审批** - 要求将审批请求发送到多个人员，让收到该请求的每个人都审批它。
- **新的 OneDrive for Business 操作** - 为 OneDrive for Business 中存储的文件生成 PDF，此外还添加了其他四个新操作。
- **Apache Impala 连接器** - Apache Impala（孵化中）是适用于 Apache Hadoop 的开源本机分析数据库。
- **添加流说明** - 提供流说明，以便在共享流时，同事可以看到流的功能摘要。

[阅读更多并询问](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/)有关此版本的问题。

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>2017 年 9 月 25 日版 - Microsoft Flow 第三季度的更新

- **首版中更深入的 SharePoint 集成** - 新增了一个现成的“请求审阅”流，此外还添加了一个 Flow 面板，针对首版租户运行某个流时，可以使用该面板收集输入。
- **Dynamics 365 for Customer Engagement** - Flow 现已与 Dynamics 365 for Customer Engagement 的 UI 相集成。
- **Microsoft 信任中心** - Flow 已列入 Microsoft 信任中心，并显示已通过 HIPAA、ISO 和 SOC 等认证。
- **使用情况分析** - 每个流已提供嵌入式 Power BI 仪表板和基本的使用情况分析。
- **首版中的审核日志记录** - 将在首版租户的 Office 365 安全性和符合性中心记录所有流管理事件。
- **六个新连接器** - 添加了 LinkedIn、Office 365 组、Skype for Business、Adobe Sign、Bizzy 和 Azure Log Analytics 数据集合。
- **SQL 触发器** - 添加了新行或者更新了 SQL 表中的行时会运行流。
- **本地自定义连接器** - 现在，自定义连接器可以使用本地数据网关连接到网络中的内部终结点。

[阅读更多并询问](https://flow.microsoft.com/blog/q3-2017-update/)有关此版本的问题。

### <a name="release-2017-09-21"></a>2017 年 9 月 21 日版

- **下载流历史记录** - 以 CSV 文件格式下载流的运行历史并在 Excel 中打开。
- **高级重复计划** - 生成触发流的重复计划，例如，仅在工作日触发。
- **IntelliSense** - 在表达式中键入内容时，IntelliSense 会提供有关参数的建议。
- **四个新连接器** - 添加了 Azure AD HTTP 服务、Amazon Redshift、Azure 事件网格发布和 FlowForma 的连接器。
- **共享链接** - 一个新操作，用于生成 OneDrive 文件或 Azure 存储 Blob 的可共享链接。

[阅读更多并询问](https://flow.microsoft.com/blog/download-history-recurrence/)有关此版本的问题。


### <a name="release-2017-08-25"></a>2017 年 8 月 25 日版
* **SharePoint 的文档属性和其他信息** - [读取和设置 SharePoint 文档库属性](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)，并使用其他字段，例如 SharePoint 项的链接。
* **流集合** - 流集合是按角色或纵轴组织的一组模板集合。
* **按钮重新共享** - 与同事共享按钮时，他们也可与其他人重新共享。
* **从按钮收集列表** - 定义选项的下拉列表，使用户在点击按钮时可从中做出选择。
* **七个新连接器** - AWeber、Azure Log Analytics、Azure 表、DocFusion365、Azure 事件网格、Azure 事件中心和 StaffHub。 
* **Slack 和 MySQL 的改进** - 在 Slack 中创建或联接通道，并可以写入 MySQL 数据库。

[阅读更多并询问](https://flow.microsoft.com/blog/button-updates-seven-connectors/)有关此版本的问题。

### <a name="release-2017-08-02"></a>2017 年 8 月 2 日版
* 写入到“人员”、“选择”和“查找”字段 - SharePoint 的 Create 项和 Update 项[现在支持的功能](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/)包括设置“人员”、“选择”和“查找”字段。
* 更多操作设置 - 现在可以更精细地控制触发器和操作的运行方式，包括配置重试策略和分页。
* 四个新的连接器 - 现在可以使用 Azure 文件存储、Elastic Forms、Plivo 和视频索引器。

[阅读更多并询问](https://flow.microsoft.com/blog/four-connector-action-settings/)有关此版本的问题。

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>2017 年 7 月 27 日版 - Microsoft Flow 第二季度的更新
* 导入和导出 - 跨环境（或从测试到生产）的导出和导入流解决方案。 
* 在操作中使用表达式 - 在任意操作中使用表达式，获取使用方面的内联帮助。
* 扩大为 Azure 逻辑应用 - 将流另存为 Azure 逻辑应用资源，以便通过 Visual Studio 或 Azure 门户进行部署。
* 管理员可见性 - 在租户中下载 Microsoft Flow 用法，准确了解流的使用位置和方法。
* Dynamics 365 中的流 - 在 Dynamics 365 for Operations & Financials, Business Edition 中使用流。
* 更轻松地查找方案 - 浏览连接器可以执行的任何操作，以及将任意触发器用作生成流的起点。

[阅读更多并询问](https://flow.microsoft.com/blog/q2-2017-update/)有关此版本的问题。

### <a name="release-2017-07-13"></a>2017 年 7 月 13 日版
* 改进了模板发布 - 将创建的任何流及其类别发布到公共库。
* 获取 Outlook 日历上的事件 - 一项新操作，用于返回日历上两个时间之间的所有事件。
* 新的移动功能 - 在移动应用中根据需要运行流，以及重新提交失败的运行。
* 自定义连接器中的动态下拉列表 - 生成动态下拉列表、轮询触发器，以及测试自定义连接器。

[阅读更多并询问](https://flow.microsoft.com/blog/publishing-and-custom-connectors/)有关此版本的问题。

### <a name="release-2017-06-28"></a>2017 年 6 月 28 日版
* 更新语言设置 - 可以通过“设置”菜单自定义 Microsoft Flow 所用的“语言”和“区域”。
* 五个新的连接器 - 增加了对 Adobe Creative Cloud、必应地图、必应搜索、JotForm 和 Freshservice 的支持。
* 配置超时 - 更改长时间运行的操作（例如审批）的运行“超时”时间，使流能够持续运行。
* 在 Outlook 中提供针对审批的注释 - 收到审批请求时，不离开 Outlook 即可提供注释。
* 自定义连接器品牌颜色 - 现在可以输入适用于自定义连接器的颜色，用作背景色。
* 适用于团队流的“另存为”- 生成包括团队流在内的任何流的副本
* 删除流信息 - 删除某个流时，系统会显示该流的所有挂起运行的列表。
* 在“连接器”页上筛选 - 在“连接器”页上搜索所要的连接器，按连接器类型进行筛选。

[阅读更多并询问](https://flow.microsoft.com/blog/language-settings-3-connectors/)有关此版本的问题。

### <a name="release-2017-06-19"></a>2017 年 6 月 19 日版
现在可以查看所有已发送的挂起审批请求的状态。 此外，还可以直接从移动设备浏览所有挂起的审批并对其进行操作。

[阅读更多并询问](https://flow.microsoft.com/blog/sent-requests-flow-mobile/)有关此版本的问题。

### <a name="release-2017-06-15"></a>2017 年 6 月 15 日版
* 内容转换 - 推出了新的连接器，可以将 HTML 内容转换为纯文本，适用于处理 HTML 格式的电子邮件。
* 三个新的数据库连接器 - 增加了对 MySQL、PostgreSQL 和 Teradata 的只读支持。 这些连接器通过本地数据网关进行连接。
* 三个其他的连接器 - 连接到 Azure Application Insights、Calendly 和 Teamwork Projects。
* 改进错误处理的可视化效果 - 在错误之后运行的步骤现在显示为红色虚线箭头，便于标识。
* “运行详细信息”窗格 - 当流故障时，现在会出现一个新的右窗格，其中包含一些有用的步骤，说明如何纠正流的错误。

[阅读更多并询问](https://flow.microsoft.com/blog/seven-connectors-and-html/)有关此版本的问题。

### <a name="release-2017-06-04"></a>2017 年 6 月 4 日版
* 适用于 Windows Phone 的 GA 版 - [Microsoft Flow 移动应用现已发布，提供适用于 Windows Phone 的公开发行版](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/)。
* 在流故障时获得电子邮件通知 - 当流故障时，系统会通过电子邮件通知你。 这些故障电子邮件一周只会发送一次，用户可以打开或关闭此功能。
* 适用于表的“选择”操作 - 使用新的“选择”操作，更改要包括在表中的列集。
* Microsoft Forms 连接器 -  Microsoft Forms 是 Office 365 教育版新的组成部分，允许教师和学生快捷地创建自定义测验，以及创建调查、调查表、注册等。
* Office 365 企业版 K1 计划 - PowerApps 和 Microsoft Flow 现在包括在 Office 365 企业版 K1 计划中，有特定的配额限制。
* HTTP 标头使用更方便 - 填充要操作的文本框即可提供标头名称和标头值，就像“选择”操作一样。

[阅读更多并询问](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/)有关此版本的问题。

### <a name="release-2017-05-23"></a>2017 年 5 月 23 日版
* **Microsoft Teams 连接器** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) 是 Office 365 中一个以聊天为主的工作区，其作用是将人员、对话、内容以及团队所需的工具汇集在一起，方便大家合作，提高工作效率。
* **iOS 和 Android 上的小组件** - Microsoft Flow 小组件是按钮快捷方式，适用于轻松快捷地直接从主屏幕触发按钮。
* **创建“错误处理”步骤** - 定义一个或多个在操作失败后运行的步骤。 例如，当流在 Dynamics 365 中创建记录失败时，立即向你发送通知。
* **整数和浮点变量** - 对流运行中用于对某组逻辑运行计数的计数器进行初始化和递增/递减操作。
* **流详细信息页** - 在“我的流”列表中选择某个流时，将会显示一个页面，详细介绍该流的情况，例如谁具有访问权限，以及运行历史记录。
* **管理员的流运行配额** - 管理员现在可以根据常用的公司运行配额来监视整个组织的流运行使用情况，并通过配额明细来了解其配额中各个许可证的贡献。
* **HTTP 请求触发器改进** - 使用不同的 HTTP 方法，并为请求触发器添加路径段。
* **两个合作伙伴连接器** - Microsoft Flow 现在可以连接到 Parserr（电子邮件分析服务）和 Cognito Forms（联机窗体服务）。

[阅读更多并询问](https://flow.microsoft.com/blog/error-handling/)有关此版本的问题。

### <a name="release-2017-05-12"></a>2017 年 5 月 12 日版
* **SharePoint 文档库集成** - 可以在文档库中选择任何文件，然后启动一个流，例如，将其发送到经理处进行审批，[等等](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/)。
* **Microsoft Planner 连接器** - 可以使用 Microsoft Planner 轻松地将团队、任务、文档和对话集中在一起，以便获得更好的结果。
* **管理员许可证视图** - 管理员可以在 Microsoft 流管理中心查看所有 Microsoft Flow 和 PowerApps 许可证（包括试用版和付费版）。
* **PowerApps 社区计划** - PowerApps 社区计划是一项免费的计划，目的是方便各个用户浏览、学习和积累 PowerApps、Microsoft Flow 和 Common Data Service 方面的技能。

[阅读更多并询问](https://flow.microsoft.com/blog/planner-community-and-licenses/)有关此版本的问题。

### <a name="release-2017-05-09"></a>2017 年 5 月 9 日版
* **Azure AD 连接器** -推出了新的连接器，可以通过 Microsoft Flow 执行管理员操作，包括创建用户或将其添加到组。
* **Office 365 Outlook 改进** - 现在可以通过共享邮箱来触发流，还可以通过流将邮件发送到共享邮箱。 流也可以设置或读取自动答复。
* **在加拿大推出** - 现在可以在加拿大创建流。
* **创建自定义 API Webhook** - 自定义连接器开发人员现在可以通向 Webhook 向自定义 API 添加触发器。
* **在管理中心管理流所有者** - 环境管理员可以在 Microsoft Flow 管理中心管理流所有者。
* **连接器文档参考** - 我们现已[在 docs.microsoft.com 上提供完整的连接器参考](https://docs.microsoft.com/Connectors/)。
* **两项合作伙伴服务** - 已发布两项新的合作伙伴服务：Nexmo 和 Paylocity。

[阅读更多并询问](https://flow.microsoft.com/blog/canada-mailboxes-aad)有关此版本的问题。

### <a name="release-2017-04-27"></a>2017 年 4 月 27 日版
* **通过并行步骤生成流** - 以并行执行的方式创建流：即你可以同时运行两个或两个以上的步骤。
* **支持五项新服务** - 五项新服务：审批、Benchmark Email、Capsule CRM、LiveChat 和 Outlook Customer Manager。
* **监视操作的重试** - 服务故障时，Microsoft Flow 会重试。 现在可以查看自动重试的次数以及所发生情况的详细信息。

[阅读更多并询问](https://flow.microsoft.com/blog/parallel-actions/)有关此版本的问题。

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>2017 年 4 月 17 日版 - Microsoft Flow 第一季度的更新
* **现代审批体验** - 创建工作流，以便审批者可以通过 Microsoft Flow 移动应用或 Microsoft Flow 网站上的统一审批中心进行安全的审批。
* **团队流公开发布** - 团队流现已公开发布，方便多人共同拥有并管理一个流。
* **生成 Microsoft Flow 的连接器** - 任何人都可以提交自己的 Microsoft Flow 连接器，供全世界的用户免费使用。
* **“简约”设计器** - 新版设计器针对特定模板，仅提供创建流时必填的字段，简化体验。

[阅读更多并询问](https://flow.microsoft.com/blog/q1-2017-update/)有关此版本的问题。

### <a name="release-2017-04-11"></a>2017 年 4 月 11 日版
* **用于构建表和列表的新操作** - 新增了可以处理项列表的“创建 HTML 表”、“创建 CSV 表”和“联接”操作（而不是只有以前的“应用到每一个”）。
* **在任意位置插入步骤** - 现在可以在工作流中的任意位置插入新步骤而无需执行拖放操作。
* **四个新服务** - Flow 现在支持 10 to 8 Scheduling、Act!、Inoreader 和计算机视觉 API。 有了计算机视觉 API，就可以处理图像来获取文本内容（称为 OCR），或者基于图像内容自动标记图像。

[阅读更多并询问](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/)有关此版本的问题。

### <a name="release-2017-04-03"></a>2017 年 4 月 3 日版
* **Windows Phone Beta** - Windows Phone 应用 Beta 程序已发布，可以用于预览 Windows Phone 上的应用。 [阅读详细信息](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/)。
* **Muhimbi PDF** - 现在可以通过 Muhimbi PDF 将 Microsoft Word 文件转换为 PDF、添加水印、合并文档等。 [阅读详细信息](https://flow.microsoft.com/blog/convert-files-using-muhimbi/)。
* **从物理按钮触发流** - 宣布与物理按钮领域的两大领先的产品公司（Flic by Shortcut Labs 和 Bttn by The Button Corporation）建立合作关系。 [阅读详细信息](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>2017 年 3 月 22 日版
* **复制流** - 现在可以通过复制流在草稿版上工作，或者复制在过去创建的流。
* **两项新服务** - 增加了对 Toodledo 的支持，以便通过创建和更新任务来管理待办事项列表；同时增加了对 Zendesk 的支持，以便提供客户服务和支持票证平台。

[阅读更多并询问](https://flow.microsoft.com/blog/make-a-copy/)有关此版本的问题。

### <a name="release-2017-03-15"></a>2017 年 3 月 15 日版
* **与同事共享按钮** - 现在允许与他人共享流按钮，方便业务用户执行快速任务。
* **从主屏幕触发按钮** - 在移动设备的主屏幕和锁屏界面中提供流按钮的快捷方式，加快流的触发速度。
* **在 Microsoft Flow 应用中启用团队流** - 现在可以在适用于 iOS 或 Android 的 Microsoft Flow 应用中为流添加其他所有者。

[阅读更多并询问](https://flow.microsoft.com/blog/button-sharing/)有关此版本的问题。

### <a name="release-2017-03-10"></a>2017 年 3 月 10 日版
* **改进自定义连接器体验** - 现在可以使用 Postman Collection 创建自定义连接器，并可编辑、添加和测试操作。
* **两项新服务** - 增加了 PowerApps Notifications 和 PivotalTracker 支持。

[阅读更多并询问](https://flow.microsoft.com/blog/new-updates-custom-api/)有关此版本的问题。

### <a name="release-2017-02-27"></a>2017 年 2 月 27 日版
* **触发流按钮** - 现在可以直接从 Microsoft Flow 网站触发流按钮。 查看流的列表时，可直接选择“...”菜单，然后选择“立即运行”命令。
* **五项新服务** - 增加了 Oracle 数据库、Intercom、FreshBooks、LeanKit 和 WebMerge 支持。

[阅读更多并询问](https://flow.microsoft.com/blog/trigger-flow-buttons-web/)有关此版本的问题。

### <a name="release-2017-02-21"></a>2017 年 2 月 21 日版
* **查看环境流** - 环境管理员现在可以查看包含给定环境中所有流的完整列表，并可启用、禁用或删除流。
* **两项新服务** - 增加了 Azure 自动化和 Basecamp 2 支持。

[阅读更多并询问](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)有关此版本的问题。

### <a name="release-2017-02-16"></a>2017 年 2 月 16 日版
* **五项新服务** - 增加了对 Azure Data Lake、Bitbucket（一项基于 Web 的托管服务，适用于使用 GIT 修订控制的项目）、Eventbrite、Infusionsoft 和 Pipedrive 的支持。
* **自定义 HTTP 身份验证** - 在流设计器中，现在可以对自定义 HTTP 终结点使用身份验证。
* **分析 JSON 消息** - 可以分析从 HTTP 请求触发器获取的或从 HTTP 操作返回的 JSON 数据。
* **流运行筛选** - 改进了流运行的筛选，提供了更具体的选项，包括查看正在运行的流或已取消的运行。

[阅读更多并询问](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)有关此版本的问题。

### <a name="release-2017-02-06"></a>2017 年 2 月 6 日版
* **团队流** - 使用团队流，多个人可以共同拥有并管理流，如果有人离开组织，他们创建的流可以继续运行。
* **共享自定义连接器** - 自定义连接器，如团队流，可以在组织内共享和共同管理。
* **Gmail 和 LUIS 支持** - 连接到 Gmail 和 Azure 认知服务的语言理解智能服务。

[阅读更多并询问](https://flow.microsoft.com/blog/team-flows/)有关此版本的问题。

### <a name="release-2017-01-30"></a>2017 年 1 月 30 日版
* **流按钮输入** - 流按钮现在可以在运行时接收用户输入，因此流作者可以定义在点击按钮时传入的信息。
* **Outlook 任务和 HelloSign** - Outlook 任务服务让你可以管理任务，而 HelloSign 使你能够使用安全的电子签名。

[阅读更多并询问](https://flow.microsoft.com/blog/button-user-inputs/)有关此版本的问题。

### <a name="release-2017-01-23"></a>2017 年 1 月 23 日版
* **按服务搜索** - 通过添加触发器或操作来查看每个服务的所有操作时，按服务进行浏览。
* **Switch 用例** - 添加 Switch 块，设置并行逻辑的多个分支。
* **更多电子邮件操作** - 在 Office 365 Outlook 和 Outlook.com 服务中新增了适用于已标记邮件的功能。
* **五项新服务** - 连接到本地或网络文件系统、支付服务 Stripe、IBM Informix、IBM DB2 和 UserVoice。

[阅读更多并询问](https://flow.microsoft.com/blog/search-by-service/)有关此版本的问题。

### <a name="release-2017-01-14"></a>2017 年 1 月 14 日版
* **重新提交运行** - 如果你想在某个流发生故障的情况下尝试修复并重新运行该流，则可重新提交发生故障的运行。
* **取消运行** - 现在，当流出现故障时，可以显式取消运行。
* **两项新服务** - 增加了对 GoToTraining 和 GoToWebinar 的支持。
* **移动链接** - 可以直接从移动应用共享模板。我们已在网站顶部添加了应用的快速下载链接。

[阅读更多并询问](https://flow.microsoft.com/blog/managing-runs/)有关此版本的问题。

### <a name="release-2016-12-29"></a>2016 年 12 月 29 日版
Microsoft Flow 现在支持 DocuSign（用于电子签名和数字交易管理）、SurveyMonkey（用于网络调查）以及笔记应用 OneNote（仅限企业帐户）。

[阅读更多并询问](https://flow.microsoft.com/blog/final-2016-services/)有关此版本的问题。

### <a name="release-2016-12-20"></a>2016 年 12 月 20 日版
* **现在运行** - 用户现在可以根据需要启动定期触发器 - 例如，用户已经计划好每天运行一次报告，但**现在**也需要该报告运行一次。
* **六项新服务** - 生成的流可以连接到 MSN 天气、Medium、Google 联系人、Buffer、Harvest 和 TypeForm。

[阅读更多并询问](https://flow.microsoft.com/blog/run-now-and-six-more-services/)有关此版本的问题。

### <a name="release-2016-12-14"></a>2016 年 12 月 14 日版
用户现在可以充分利用触发按钮流时的各种重要信息，例如触发按钮的地点、人物、时间等。

[阅读更多并询问](https://flow.microsoft.com/blog/button-trigger-tokens/)有关此版本的问题。

### <a name="release-2016-12-06"></a>2016 年 12 月 6 日版
* **介绍引导式学习** - 开始学习一系列的课程，这些课程将视频与文档相结合，帮助你了解 Microsoft Flow 丰富而强大的功能。
* **两个新服务** - 流现在可以使用 Freshdesk（使用者支持解决方案）和 GoToMeeting（联机会议工具）。
* **HTTP Webhook 支持** - 流现在可以是自动注册和注销本身的 Webhook 终结点。

[阅读更多并询问](https://flow.microsoft.com/blog/guided-learning-and-two-services/)有关此版本的问题。

### <a name="release-2016-11-23"></a>2016 年 11 月 23 日版
* **Flow 中的 Power BI 警报支持** -通过从 Power BI 数据警报触发流，来实现根据信息自动执行操作。
* **移动应用程序改进** - 除了基于模板进行创建的现有体验之外，还添加了从头开始创建流的功能。 我们还提高了查看流运行时的性能。
* **八个新服务** - 现在可连接到 Azure 资源管理器、Azure 队列、Chatter、Disqus、Azure Cosmos DB、认知服务人脸 API、HipChat 以及 Wordpress。

[阅读更多并询问](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/)有关此版本的问题。

### <a name="release-2016-11-15"></a>2016 年 11月 15 日版
* **Microsoft Flow 合作伙伴计划** - Microsoft Flow 现在有一个认证的合作伙伴计划，用于增强全球各大公司杰出人才的联系，充分利用其对 Microsoft Flow 的体验。
* **六项新服务** - 本周，我们还发布了六项服务：Asana、Campfire、EasyRedmine、JIRA、Redmine 和 Vimeo。

[阅读更多并询问](https://flow.microsoft.com/blog/partner-program-six-new-services/)有关此版本的问题。

### <a name="release-2016-10-31---general-availability"></a>2016 年 10 月 31 日版 - 正式发布
* **定价和许可** - 现在同时在免费和付费套餐中提供，并包含在 Office 365 和 Dynamics 365 中。
* **Microsoft Flow 管理中心** - 新管理中心可供企业使用。 在管理中心内，可以管理组织内部的环境。
* **数据丢失防护策略** - 管理员可以创建数据丢失防护策略来控制服务之间的数据流。
* **Android 可用性** - Microsoft Flow 手机应用现已可用于 iOS 和 Android。 使用该应用可以获得通知、监视活动，并可通过点击按钮启动流。
* **新设计器体验** - 现在可以搜索分步传递的动态内容，更快地引用所需的数据。

[阅读更多并询问](https://flow.microsoft.com/blog/announcing-ga/)有关此版本的问题。

### <a name="release-2016-10-26"></a>2016 年 10 月 26 日版
* **按钮流** - 我们希望可以随时随地触发无数的操作。 现在，有了按钮流，只需从移动设备单击一个按钮即可完成。
* **公告环境** - 环境是用于存储和管理组织的流的不同空间。 环境存在于不同地点，这意味着环境中存在的流、应用和业务数据将在该环境所在的区域中。
* **六个新服务** - 添加对 Bit.ly、Cognitive Services Text Analytics、Dynamics NAV、Dynamics 365 for Financials、Instapaper 和 Pinterest 的支持。

[阅读更多并询问](https://flow.microsoft.com/blog/environments-for-makers/)有关此版本的问题。

### <a name="release-2016-10-16"></a>2016 年 10 月 16 日版
* **自定义连接器支持多个身份验证类型** - 自定义连接器现在支持 API 密钥身份验证，并可以对任何支持完整 OAuth 2.0 规范的服务进行身份验证。
* **支持的三个新服务** - 增加了对 Basecamp 3、Blogger 和 PagerDuty 的支持。
* **设计器改进** - 性能得到改善，现在，用户可直接从每个操作的"..."菜单更新和修复连接，并且我们还新增了一个名为“终止”的步骤，该步骤可用于结束流运行。

[阅读更多并询问](https://flow.microsoft.com/blog/early-october-updates/)有关此版本的问题。

### <a name="release-2016-09-25"></a>2016 年 9 月 25 日版
现在，可以从移动电话创建流。 浏览我们丰富的模板库、服务列表，或选择模板类别进行深入了解。 [阅读更多并询问](https://flow.microsoft.com/blog/mobile-creation/)有关此版本的问题。

### <a name="release-2016-09-22"></a>2016 年 9 月 22 日版
* **Microsoft Graph 人员选择器** - 新的 Microsoft Graph 人员选择器直接集成到 Microsoft Flow UI，以帮助选择正确的联系人或电子邮件地址。
* **Microsoft Dynamics AX 支持** - 现在，可从流内部对 Dynamics AX 在线操作数据执行操作，如创建新记录、查询数据等。
* **合作伙伴提供的两个新服务** - 现在，可从流中使用 appFigures 或 Insightly。

[阅读更多并询问](https://flow.microsoft.com/blog/more-september-updates/)有关此版本的问题。

### <a name="release-2016-09-14"></a>2016 年 9 月 14 日版
* **嵌入网站或应用** - 现在，开发人员可以将 Microsoft Flow 嵌入其应用或网站，为用户提供个人或专业任务自动化的简单方法。
* **将流用作 HTTP 终结点** - 现在，用户可将流本身用作 HTTP API。 流内部有个名为“请求”的触发器，用户可通过添加“响应”卡对传入的请求作出响应。
* **Todoist 支持** - 用户可通过 Todoist 查看所有项目，无论是在工作单位还是在家。

[阅读更多并询问](https://flow.microsoft.com/blog/extend-web-site-application/)有关此版本的问题。

### <a name="release-2016-09-01"></a>2016 年 9 月 1 日版
现在，所有人都可以使用 Microsoft Flow - 最初，我们只对工作单位或学校（使用 Office 365 Business 或 Office 365 Enterprise）提供的邮箱地址开放预览。 今天，我们宣布，所有用户都可以免费从官方下载使用预览，无论用户使用的是什么邮箱。 [阅读更多并询问](https://flow.microsoft.com/blog/available-for-everyone/)有关此版本的问题。

### <a name="release-2016-08-31"></a>2016 年 8 月 31 日版
* **嵌套条件** - 现在，用户可将第二个（或第三个，等等）条件内嵌到其他条件中。
* **应用到每个** - 通过“应用到每个”循环可控制重复的列表。
* **操作停止条件** - 通过“操作停止条件”循环可重复某一步骤，直到满足一定条件。
* **筛选阵列** - 存在单个本地筛选步骤，可确保列表中的每一项都与定义的表达式相匹配。
* **编写字符串变量** - 现在，用户可以编写字符串变量。
* **作用域** - 作用域是将两个或多个操作归为一组的简单方法。

[阅读更多并询问](https://flow.microsoft.com/blog/build-advanced-flows/)有关此版本的问题。

### <a name="release-2016-08-27"></a>2016 年 8 月 27 日版
* **步骤注解** - 注解使得通过注释对每个单独操作进行批注变得非常容易，这样可以很容易记住流所需要的内容。
* **Smartsheet 支持** - 本周我们增加了对连接到 Smartsheet 的支持。 Smartsheet 是一种可在云中的工作表上轻松协作的服务。
* **编写流时的 UI 优化** - 我们已将流名称放到前面中间的位置，并将“保存”按钮移至页面顶部，以方便访问。

[阅读更多并询问](https://flow.microsoft.com/blog/add-comments-smartsheet/)有关此版本的问题。

### <a name="release-2016-08-18"></a>2016 年 8 月 18 日版
现在，用户可以预览包含 Microsoft Flow 集成的 SharePoint Online 现代列表体验。 [阅读更多并询问](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/)有关此版本的问题。

### <a name="release-2016-08-13"></a>2016 年 8 月 13 日版
* **Visual Studio Team Services** - 现在，用户可以通过使用 Microsoft Flow 将 VSTS 连接到 O365 Email、Slack、Trello 和 Wunderlist 等各种服务。
* **SharePoint 的增强功能** - SharePoint 列表支持多种数据类型，这些数据类型不仅包括文本单线以及日期和时间等简单对象，也包括人员或组、查找以及选择等复杂对象。
* **测试 O365 Outlook 连接** - 用户创建新的 O365 Outlook 连接后，我们可立即对其进行测试，以确保用户已做好使用连接的准备。
* **布尔控件** - 我们还新增了布尔控件，以阐明用户应在布尔输入字段中键入的值，如“当收到新电子邮件时”触发器中的“有附件”。

[阅读更多并询问](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/)有关此版本的问题。

### <a name="release-2016-08-08"></a>2016 年 8 月 8 日版
公共预览版的 Microsoft 通用数据服务集成到 Microsoft Flow 中。 [阅读更多并询问](https://flow.microsoft.com/blog/flow-and-common-data-model/)有关此版本的问题。

### <a name="release-2016-08-05"></a>2016 年 8 月 5 日版
* **本地 SharePoint** - 与 SharePoint Online 的使用方法一样，用户可以使用预定义模板或从头构建模板来创建有关 SharePoint 本地列表和文档库的流。
* **设计器中的信息气泡** - 为了阐述每个触发器和操作的功能，我们在流的每个步骤的上方增加了信息气泡。

[阅读更多并询问](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/)有关此版本的问题。

### <a name="release-2016-07-15"></a>2016 年 7 月 15 日版
* **新增了四个服务** - 连接到 Google 日历、Google 任务管理器、YouTube 以及 SparkPost。
* **重命名操作** - 现在，用户可通过对这些操作重命名来其进行区分。
* **不同时间段的延迟** - 现在，用户可以选择任意秒数、分钟数、小时数或天数。
* **更易于使用文件夹浏览器** - 我们简化了文件夹浏览器。现在，在左侧选择可选择该文件夹，在右侧选择可打开该文件夹，以便选择其中的子文件夹。

[阅读更多并询问](https://flow.microsoft.com/blog/new-google-services-rename-more/)有关此版本的问题。

### <a name="release-2016-07-08"></a>2016 年 7 月 8 日版
使用本地数据网关从本地连接 Microsoft Flow。 这样，用户可以建立到 SQL Server 的安全连接，并将它们与流集成。 [阅读更多并询问](https://flow.microsoft.com/blog/on-premises-data-gateway/)有关此版本的问题。

### <a name="release-2016-07-02"></a>2016 年 7 月 2 日版
* **Google 工作表支持** - 过去，我们已经能够使用 Excel，以及 Google Drive，但本周我们将增加本地 Google 工作表支持。
* **从模板更快速地开始** - 我们还对从模板开始的方式进行了一些优化。 现在，用户可以直接在模板页面上为内联的模板选择要使用的帐户。
* **不再有 SharePoint 和 Office 365 授权到期** - 现在，Microsoft Flow 将自动更新用户对基于 Azure Active Directory 的服务的访问权限，因此所有流都将在密码更改后继续工作。

[阅读更多并询问](https://flow.microsoft.com/blog/more-june-updates/)有关此版本的问题。

### <a name="release-2016-06-20"></a>2016 年 6 月 20 日版
* **为 Microsoft Flow 引入新的移动应用** - 今天，我们非常高兴地介绍我们的产品的另一个主要部分：现在可在 iOS 系统上下载的一款移动应用（很快也可以在 Android 系统上下载），通过使用该应用，用户可以随时随地管理、跟踪以及浏览自动化工作流。  
* **单点登录** - 我们已实施单点登录，用户可以通过 Office 365 等其他 Microsoft 服务进行 Microsoft Flow 身份验证。

[阅读更多并询问](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/)有关此版本的问题。

### <a name="release-2016-06-18"></a>2016 年 6 月 18 日版
* **新邮件服务** - 现在，用户可以直接从 Microsoft Flow 发送电子邮件，无需连接到 Microsoft Flow 中的个人或工作邮箱帐户。
* **门户中的通知** - 现在，每当出现与流断开的情况时，用户都将在门户的顶部看到通知。
* **门户中的所有活动** - 现在，用户可以通过单击流网站中的“活动”选项卡查看所有流中的活动。

[阅读更多并询问](https://flow.microsoft.com/blog/mail-and-all-activity/)有关此版本的问题。

### <a name="release-2016-05-27"></a>2016 年 5 月 27 日版
* **按服务浏览模板** - 现在有一种方法可以查看我们支持的所有服务（无需登录）。 在此页面中，用户可以看到每个服务的说明，并检查该服务的模板。
* **创建和使用自定义连接器** - 与在 PowerApps 中创建自定义连接器一样，你也可以直接连接到自己的位于 flow.microsoft.com 的 API：
* **在完成之前测试流** - 现在，保存流时，如果执行启动操作，用户可以看到页面中的实时流运行结果。

[阅读更多并询问](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/)有关此版本的问题。

### <a name="release-2016-05-07"></a>2016 年 5 月 7 日版
新增了两项服务：Microsoft Project Online 以及 Mailchimp 的 Mandrill。 [阅读更多并询问](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/)有关此版本的问题。

### <a name="release-2016-04-27---public-preview"></a>2016 年 4 月 27 日版 - 公开预览版
如果已使用过 [Microsoft PowerApps](https://powerapps.microsoft.com) 中的逻辑流，则会发现 Microsoft Flow 预览版提供多项新功能：

* 现在，用户可以浏览包含数十个模板的库，并按“受欢迎程度”、“名称”或“发布日期”排序。
* 自定义流以后，即可[将自己的模板发布](publish-a-template.md)到库中。
* 可以查看每次检查和运行流的历史记录。
* 保存流以后，直接执行触发器操作即可[立即观看运行中的流](see-a-flow-run.md)。
* 成立了一个[新社区](https://go.microsoft.com/fwlink/?LinkID=787467)，方便用户讨论 Microsoft Flow 或[提交意见](https://go.microsoft.com/fwlink/?LinkID=787474)。

## <a name="next-steps"></a>后续步骤
如果有任何问题未在这些发行说明或[常见问题](frequently-asked-questions.md)中讲到，请[加入社区](https://go.microsoft.com/fwlink/?LinkID=787467)提问问题，或[联系支持部门](http://go.microsoft.com/fwlink/?LinkID=787479)。

