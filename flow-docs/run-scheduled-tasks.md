---
title: "按计划运行流 | Microsoft Docs"
description: "按计划运行流，例如每天运行一次流，或者每小时运行一次流，自动执行重复的任务。"
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: stepsic
ms.openlocfilehash: eaeaf62da694daf7f8e6d876c3d225337fdbe592
ms.sourcegitcommit: 01325305b9d2cf964acac9feb6cca0af66db7440
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2017
---
# <a name="run-flows-on-a-schedule"></a>按计划运行流
创建一个流，使之执行一个或多个符合以下条件的任务（例如在电子邮件中发送报表）：

* 一天、一小时或一分钟执行一次
* 在指定的日期执行
* 在指定的天数、小时数或分钟数过后执行

## <a name="create-a-recurring-flow"></a>创建重复的流
1. 登录到 [Microsoft Flow](https://flow.microsoft.com)，然后在顶部导航栏中选择“我的流”。
   
    ![“我的流”选项](./media/run-scheduled-tasks/create-flow.png)
2. 选择“从零开始创建”。
   
    ![从零开始创建流](./media/run-scheduled-tasks/create-from-blank.png)
3. 在“搜索所有连接器和触发器”框中，键入“定期”，然后选择“计划 - 定期”。
   
    ![查找定期触发器](./media/run-scheduled-tasks/select-recurrence.png)
4. 在“定期”对话框中，指定所希望的流运行频率。
   
    例如，如果希望流每两周运行一次，可在“频率”下指定“周”，在“时间间隔”下指定“2”。
   
    ![指定定期](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>指定高级选项
1. 执行上一部分的步骤，然后选择“显示高级选项”。
   
    注意：这些选项随“时间间隔”和“频率”的设置值而变。 如果你的屏幕与下图不符，请确保“时间间隔”和“频率”的设置值与图中所示相同。
2. 选择“时区”，指定是否让“开始时间”反映本地时区、协调世界时 (UTC) 等。
3. 按以下格式指定“开始时间”：
   <br>YYYY-MM-DDTHH:MM:SSZ
4. 如果已在“频率”下指定“天”，请指定一天中运行流的时间。
5. 如果已在“频率”下指定“周”，请指定一周中运行流的日期，以及一天中运行流的时间。
   
    例如，可以将选项配置如下，使流的开始时间不早于 2018 年 1 月 1 日（星期一）的中午（太平洋时间），并让流每两周在星期二下午 5:30（太平洋时间）运行一次。
   
    ![指定高级选项](./media/run-scheduled-tasks/advanced-options.png)
6. 根据[从头开始创建流](get-started-logic-flow.md)中的说明，添加希望流执行的一个或多个操作。

## <a name="delay-a-flow"></a>延迟流
1. 登录到 [Microsoft Flow](https://flow.microsoft.com)，然后在顶部导航栏中选择“我的流”。
   
    ![从零开始创建流](./media/run-scheduled-tasks/create-flow.png)
2. 选择“从零开始创建”。
   
    ![从零开始创建流](./media/run-scheduled-tasks/create-from-blank.png)
3. 根据[从头开始创建流](get-started-logic-flow.md)中的说明指定事件。
4. 选择“新建步骤”，然后选择“添加操作”。
   
    ![向流添加操作的选项](./media/run-scheduled-tasks/add-action.png)
5. 在操作列表中，执行以下任一操作：
   
   * 选择“延迟”，指定“计时”，然后指定时间的“单位”，例如秒、分钟或小时。
   * 选择“延迟到”，然后按以下格式指定日期。<br>YYYY-MM-DDTHH:MM:SSZ
     
     ![添加延迟](./media/run-scheduled-tasks/add-delay.png)
     ![按时间单位指定延迟](./media/run-scheduled-tasks/delay.png)
     ![指定“延迟到”](./media/run-scheduled-tasks/delay-until.png)

