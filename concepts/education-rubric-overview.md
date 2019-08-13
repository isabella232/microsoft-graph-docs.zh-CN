---
title: 教育版评分标准概述
description: 评分标准是一种被广泛采用的有效作业评分方式，Microsoft Graph 中的教育版 API 支持它们。
author: mmast-msft
localization_priority: Priority
ms.prod: education
ms.openlocfilehash: 56b9bcdf32036361fb92fe372952c94d09d8dc57
ms.sourcegitcommit: 129e58f83fc566f9d9f36e26b0c0b8cdf81d27d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2019
ms.locfileid: "36173081"
---
# <a name="education-rubric-overview"></a>教育版评分标准概述

评分标准是一种被广泛采用的有效作业评分方式，Microsoft Graph 中的教育版 API 支持它们。

评分标准是一个*质量*、*级别*和*条件*矩阵，如下所示：

| | 级别 | 级别 |
|:--|:--|:--|
| 质量 | 条件 | 条件 |
| 质量 | 条件 | 条件 |

评分标准示例如下：

| | 良好 | 较差 |
|:--|:--|:--|
| 参数 | 文章的参数具有说服力。 | 文章的参数毫无意义。 |
| 拼写和语法 | 文章使用正确的拼写和语法，几乎没有或者完全没有错误。 | 文章中有许多拼写和/或语法错误。 |

使用评分标准的评分涉及为评分标准中的每种*质量*选择一个*级别*。

评分标准*可能*具有与每个级别关联的点数以及与每个质量关联的权重。  如果存在，权重加起来必须等于 100。

| | 良好（2 点） | 较差（1 点） |
|:--|:--|:--|
| 参数（权重 50） | 文章的参数具有说服力。 | 文章的参数毫无意义。 |
| 拼写和语法（权重 50） | 文章使用正确的拼写和语法，几乎没有或者完全没有错误。 | 文章中有许多拼写和/或语法错误。 |

## <a name="api-reference"></a>API 参考

若要开始使用评分标准，请首先了解 [Microsoft Graph beta 中的 educationRubric 资源](/graph/api/resources/educationrubric?view=graph-rest-beta)及相关方法。





 
