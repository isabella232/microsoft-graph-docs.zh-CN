---
title: printerDefaults 资源类型
description: 代表打印机的默认设置。 检查打印机的功能，以查看它支持的所有值。
author: braedenp-msft
localization_priority: Normal
ms.prod: universal-print
doc_type: resourcePageType
ms.openlocfilehash: 76f1fdd3bc773a684a29d92c9e22d363a13c11a5
ms.sourcegitcommit: 3b9eb50b790d952c7f350433ef7531d5e6d4b963
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48727955"
---
# <a name="printerdefaults-resource-type"></a>printerDefaults 资源类型

命名空间：microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

代表打印机的默认设置。 检查打印机的 [功能](printercapabilities.md) ，以查看它支持的所有值。

## <a name="properties"></a>属性
| 属性     | 类型        | 说明 |
|:-------------|:------------|:------------|
|copiesPerJob|Int32|每个作业打印的默认副本数。|
|contentType|String|处理文档时要使用的默认内容 (MIME) 类型。|
|finishings|printFinishing 集合|要应用于打印作业的默认 finishings 集。 有效值如下表所述。|
|mediaColor|String|默认媒体 (如打印文档的纸张) 颜色。
|mediaType|String|默认媒体 (（如纸张) 类型）打印文档。 有效值如下表所述。|
|mediaSize|String|要使用的默认媒体大小。 支持 ISO 和 ANSI 媒体大小的标准大小名称，以及关联打印机支持的任何自定义大小。
|pagesPerSheet|Int32|每张纸上要打印的文档页面的默认数量。
|orientation|printOrientation|打印文档时使用的默认方向。 有效值如下表所述。|
|outputBin|String|要放置的默认输出纸盒已完成打印。 请参阅打印机的 [功能](printercapabilities.md) ，获取受支持的输出箱列表。|
|fitPdfToPage|布尔|默认的 fitPdfToPage 设置。 如果为 True，则将 PDF 文档的每个页面放置到一个物理纸上;假以让打印机决定如何布置印象。|
|multipageLayout|printMultipageLayout|每个工作表打印多个页面时对页面进行布局的默认方向。 有效值如下表所述。|
|colorMode|printColorMode|打印文档时使用的默认颜色模式。 有效值如下表所述。|
|品质|printQuality|打印文档时使用的默认质量。 有效值如下表所述。|
|duplexMode|printDuplexMode|打印文档时使用的默认双面打印 (双面) 配置。 有效值如下表所述。|
|dpi|Int32|打印作业时使用的默认分辨率（以 DPI 为单位）。|
|scaling|printScaling|指定打印机如何缩放文档数据以与请求的媒体相匹配。 有效值如下表所述。|

### <a name="printmultipagelayout-values"></a>printMultipageLayout 值

|成员|值|说明|
|:---|:---|:---|
|clockwiseFromTopLeft|0|从左上角开始沿顺时针方向的网格排列页面。|
|counterClockwiseFromTopLeft|1|在从左上角开始的逆时针网格中排列页面。|
|counterClockwiseFromTopRight|双面|从右上部开始以逆时针网格线排列页面。|
|clockwiseFromTopRight|第三章|从右上部开始沿顺时针网格排列页面。|
|counterClockwiseFromBottomLeft|4 |从左下角开始以逆时针网格线排列页面。|
|clockwiseFromBottomLeft|5 |从左下角开始沿顺时针方向的网格排列页面。|
|counterClockwiseFromBottomRight|6 |从右下角开始以逆时针网格线排列页面。|
|clockwiseFromBottomRight|7 |从右下角开始沿顺时针方向的网格排列页面。|

### <a name="printduplexmode-values"></a>printDuplexMode 值

|成员|值|说明|
|:---|:---|:---|
|flipOnLongEdge|0|打印机将双面打印，并且将沿长边翻转文档。|
|flipOnShortEdge|1|打印机将双面打印，并且将沿短边翻转文档。|
|oneSided|双面|打印机将单面打印。|

### <a name="printfinishing-values"></a>printFinishing 值

|成员|值|说明|
|:---|:---|:---|
|无|第三章|无 finishings。 包括此值等效于提供空的 finishings 集合。|
|侧|4 |使用打印机的默认装订配置对文档进行装订。|
|穿透|5 |打孔使用打印机的默认打孔配置来打孔文档。|
|包装盒|6 |将封面应用于文档。|
|绑定|7 |使用打印机的默认绑定配置绑定文档。|
|saddleStitch|8 |骑马-使用打印机的默认装订配置 stich 文档。|
|stitchEdge|9 |使用打印机的默认装订配置对文档进行边缘装订。|
|stapleTopLeft|20|将文档装订在左上角。|
|stapleBottomLeft| 21|在左下角对文档进行装订。|
|stapleTopRight|22|在右上角将文档装订在一起。|
|stapleBottomRight|上午|在右下角将文档装订在一起。|
|stitchLeftEdge|24|沿左边缘对文档进行边缘装订。|
|stitchTopEdge|word|沿上边缘对文档进行边缘装订。|
|stitchRightEdge|26|将文档沿右边缘装订。|
|stitchBottomEdge|27|对文档沿下边缘进行边缘装订。|
|stapleDualLeft|28|将文档沿左边缘两次装订。|
|stapleDualTop|29|将文档沿上边缘两次装订。|
|stapleDualRight|30|将文档沿右边缘两次装订。|
|stapleDualBottom|31|将文档沿下边缘两次装订。|
|向 unknownfuturevalue|32|Evolvable 枚举 sentinel 值。 请勿使用。|

## <a name="printorientation-values"></a>printOrientation 值

|成员|值|说明|
|:---|:---|:---|
|纵|第三章|打印机将在 "纵向" 方向上打印为印记。|
|现状|4 |打印机将在 "横向" 方向上打印为印记。|
|reverseLandscape|5 |打印机将在 "翻转横向" 方向上打印为印记。|
|reversePortrait|6 |打印机将在 "反转纵向" 方向上打印为印记。|

### <a name="printquality-values"></a>printQuality 值

|成员|值|说明|
|:---|:---|
|降低|0|打印机将使用较低的 (（通常称为 "草稿"） ) 质量打印作业。|
|中等|1|打印机将使用 medim (通常称为 "普通" ) 质量打印作业。|
|高效|双面|打印机将使用高 (（通常称为 "最佳" 或 "精细" ) 质量）打印作业。|
|向 unknownfuturevalue|第三章|Evolvable 枚举 sentinel 值。 请勿使用。|

### <a name="printcolormode-values"></a>printColorMode 值

|成员|值|说明|
|:---|:---|:---|
|blackAndWhite|0|黑白 (仅使用黑色标记材料。 ) |
|灰度|1|灰度 (可能使用某些颜色标记材料。 ) |
|color|双面|颜色 (使用标记材料的任意组合来创建颜色印象) 。|
|自动|第三章|让打印机决定要使用哪种颜色模式。|

### <a name="printscaling-values"></a>printScaling 值

|成员|值|说明|
|:---|:---|:---|
|自动|0|如果文档大于所请求的媒体，且边距不为零，则打印机会缩放**文档，如 printScaling。** 否则，打印机将使用 **填充** printScaling 对文档进行缩放。 如果文档小于请求的媒体，则使用 "无" printScaling。|
|shrinkToFit|1|如果文档比请求的媒体大，则打印机会缩放文档，**如 printScaling。** 否则，打印机会缩放文档，如 **none** printScaling。|
|fill|双面|打印机缩放文档以填充请求的媒体大小，并保留其纵横比，但可能会裁剪文档的某些部分。|
|尺寸|第三章|打印机缩放文档以匹配请求媒体大小的可打印区域，并保留文档数据的纵横比而不裁剪文档。|
|无|4 |打印机不会缩放文档以适应请求的媒体大小。 如果文档大于请求的媒体，打印机会居中并剪辑生成的输出。 如果文档小于请求的媒体，则打印机会将结果输出居中。|
|向 unknownfuturevalue|5 |Evolvable 枚举 sentinel 值。 请勿使用。|

## <a name="json-representation"></a>JSON 表示形式

下面是资源的 JSON 表示形式。

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.printerDefaults"
}-->

```json
{
  "copiesPerJob": 123456,
  "contentType": "String",
  "finishings": ["String"],
  "mediaColor": "String",
  "mediaSize": "String",
  "pagesPerSheet": 123456,
  "orientation": "String",
  "outputBin": "String",
  "fitPdfToPage": true,
  "multipageLayout": "String",
  "colorMode": "String",
  "quality": "String",
  "duplexMode": "String"
}

```

## <a name="see-also"></a>另请参阅

* [restoreFactoryDefaults](../api/printer-restorefactorydefaults.md)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "printerDefaults resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

