---
title: 版式
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 3d94873931e3ee6df780df214f508258aa07a791
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735533"
---
# <a name="typography-in-wpf"></a>WPF 中的版式
本主题介绍 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的主要版式功能。 这些功能包括改进的文本呈现质量和性能、OpenType 版式支持、增强的国际文本、增强的字体支持以及新的文本应用程序编程接口（Api）。  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>改进的文本质量和性能  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的文本使用 Microsoft ClearType 呈现，从而增强了文本的清晰度和可读性。 ClearType 是由 Microsoft 开发的一种软件技术，可提高现有 Lcd （液晶显示器上显示的文本）的可读性，如笔记本电脑屏幕、Pocket PC 屏幕和平板显示器。 ClearType 使用子像素呈现，这允许通过在像素的小数部分对齐字符，以更高的保真度将文本显示为真正的形状。 超高的分辨率增加了文本显示中细节的清晰度，使其更便于长时间阅读。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的 ClearType 的另一个改进是 y 方向抗锯齿，这会平滑文本字符中浅曲线的顶部和底部。 有关 ClearType 功能的更多详细信息，请参阅[Cleartype 概述](cleartype-overview.md)。  
  
 ![采用 ClearType y 向抗锯齿的文本](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
采用 ClearType y 向抗锯齿的文本  
  
 所有文本呈现管道都可以在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中实现硬件加速，前提是计算机满足所需硬件的最低要求。 不能使用硬件执行加速的呈现会退回软件呈现。 硬件加速会影响文本呈现管道的所有阶段（从存储单个标志符号、将标志符号组合到标志符号运行、应用效果），以将 ClearType 混合算法应用于最终显示的输出。 有关硬件加速的详细信息，请参阅[图形呈现层](graphics-rendering-tiers.md)。  
  
 ![文本呈现管线示意图](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 此外，动画文本（无论是按字符还是按字形进行动画处理）可充分利用由 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 启用的图形硬件功能。 因此，可生成平滑的文本动画。  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>丰富的版式  
 OpenType 字体格式是 TrueType®字体格式的扩展。 OpenType 字体格式由 Microsoft 和 Adobe 共同开发，提供丰富的高级版式功能。 <xref:System.Windows.Documents.Typography> 对象公开了 OpenType 字体的许多高级功能，如样式替代和花体。 Windows SDK 提供了一组结合了丰富功能的示例 OpenType 字体，如 Pericles 和 Pescadero 字体。 有关详细信息，请参阅[示例 OpenType 字体包](sample-opentype-font-pack.md)。  
  
 Pericles OpenType 字体包含其他一些标志符号，它们提供标准字形集的样式备用项。 以下文本显示样式备用字形。  
  
 ![使用 OpenType 样式备用字形的文本](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "使用 OpenType 样式备用字形的文本")  
  
 花体是使用精美修饰的装饰性字形，通常与书法相关。 以下文本显示 Pescadero 字体的标准和花体字形。  
  
 ![使用 OpenType 标准字形和花体连字的文本](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "使用 OpenType 标准和花体连字的文本")  
  
 有关 OpenType 功能的更多详细信息，请参阅[Opentype 字体功能](opentype-font-features.md)。  
  
<a name="Enhanced_International_Text_Support"></a>   
## <a name="enhanced-international-text-support"></a>增强的国际文本支持  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 通过提供下列功能来提供增强的国际文本支持：  
  
- 使用自适应测量功能，在所有书写系统中实现自动行距调整。  
  
- 对国际文本的广泛支持。 有关详细信息，请参阅 [WPF 的全球化](globalization-for-wpf.md)。  
  
- 根据不同的语言进行分行、连字和对齐。  
  
<a name="Enhanced_Font_Support"></a>   
## <a name="enhanced-font-support"></a>增强的字体支持  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 通过提供下列功能来提供增强的字体支持：  
  
- 所有文本均采用 Unicode。 字体行为和选择不再需要字符集或代码页。  
  
- 字体行为与全局设置（如系统区域设置）无关。  
  
- 分隔 <xref:System.Windows.FontWeight>、<xref:System.Windows.FontStretch>和 <xref:System.Windows.FontStyle> 类型以便定义 <xref:System.Windows.Media.FontFamily>。 这比 Win32 编程提供了更大的灵活性，其中斜体和粗体的布尔组合用于定义字体系列。  
  
- 在处理书写方向（横向与纵向）时不受字体名称的影响。  
  
- 使用复合字体技术在可移植 XML 文件中链接字体和字体回退。 使用复合字体可以构造全面的多语言字体。 复合字体还提供一种可避免显示缺失字形的机制。 有关详细信息，请参阅 <xref:System.Windows.Media.FontFamily> 类中的备注。  
  
- 使用一组单语言字体，根据复合字体生成国际字体。 在开发多语言字体时，该功能可节省资源成本。  
  
- 在文档中嵌入复合字体，从而能够提供文档可移植性。 有关详细信息，请参阅 <xref:System.Windows.Media.FontFamily> 类中的备注。  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>新的文本应用程序编程接口 (API)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了多个文本 Api，供开发人员在其应用程序中包含文本时使用。 这些 Api 分为三个类别：  
  
- **布局和用户界面**。 图形用户界面（GUI）的通用文本控件。  
  
- **轻量文本绘制**。 可直接在对象上绘制文本。  
  
- **高级文本格式设置**。 可实现自定义文本引擎。  
  
### <a name="layout-and-user-interface"></a>布局和用户界面  
 在功能的最高级别，文本 Api 提供常见 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 控件，如 <xref:System.Windows.Controls.Label>、<xref:System.Windows.Controls.TextBlock>和 <xref:System.Windows.Controls.TextBox>。 这些控件提供应用程序中的基本 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 元素，并提供一种表示文本和与文本交互的简便方法。 控件（如 <xref:System.Windows.Controls.RichTextBox> 和 <xref:System.Windows.Controls.PasswordBox>）可实现更高级或专用的文本处理。 和类（如 <xref:System.Windows.Documents.TextRange>、<xref:System.Windows.Documents.TextSelection>和 <xref:System.Windows.Documents.TextPointer>）启用有用的文本操作。 这些 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 控件提供 <xref:System.Windows.Controls.Control.FontFamily%2A>、<xref:System.Windows.Controls.Control.FontSize%2A>和 <xref:System.Windows.Controls.Control.FontStyle%2A>等属性，使您能够控制用于呈现文本的字体。  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>使用位图效果、转换和文本效果  
 通过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，可以借助位图效果、转换和文本效果等功能，来创建悦目的文本用法。 下面的示例演示了应用于文本的典型类型的投影效果。  
  
 ![柔和度&#61;为0.25 的文本阴影](./media/typography-in-wpf/drop-shadow-text-effect.jpg) 
  
 下面的示例演示了应用于文本的投影效果和噪音。  
  
 ![有噪音的文本阴影](./media/typography-in-wpf/drop-shadow-noise-text.jpg) 
  
 下面的示例演示了应用于文本的外发光效果。  
  
 ![使用 OuterGlowBitmapEffect 的文本阴影](./media/typography-in-wpf/text-shadow-glow-effect.jpg)
  
 以下示例显示了应用于文本的模糊效果。  
  
 ![使用 BlurBitmapEffect 的文本阴影](./media/typography-in-wpf/text-shadow-blur-effect.jpg)  

 下面的示例演示沿 X 轴放大 150% 得到第二行文本，沿 Y 轴放大 150% 得到第三行文本。  
  
 ![使用 ScaleTransform 缩放的文本](./media/typography-in-wpf/scaled-text-scaletransform.jpg) 
  
 以下示例演示沿 X 轴倾斜的文本。  
  
 ![使用 SkewTransform 扭曲的文本](./media/typography-in-wpf/skewed-transformed-text.jpg)
  
 <xref:System.Windows.Media.TextEffect> 对象是一个帮助器对象，它允许您将文本视为文本字符串中的一个或多个字符组。 下面的示例演示发生旋转的单个字符。 每个字符都将以 1 秒为间隔单独旋转。  
  
 ![旋转文本的文本效果屏幕快照](./media/typography-in-wpf/rotating-text-effect.jpg) 
  
#### <a name="using-flow-documents"></a>使用流文档  
 除了常见 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 控件外，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还提供了一个用于文本呈现的布局控件，即 <xref:System.Windows.Documents.FlowDocument> 元素。 <xref:System.Windows.Documents.FlowDocument> 元素与 <xref:System.Windows.Controls.DocumentViewer> 元素结合使用，可为具有不同布局要求的大量文本提供控件。 布局控件通过其他 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 控件的 <xref:System.Windows.Documents.Typography> 对象和字体相关属性提供对高级版式的访问。  
  
 下面的示例演示了在 <xref:System.Windows.Controls.FlowDocumentReader>中承载的文本内容，它提供了搜索、导航、分页和内容缩放支持。  
  
 ![显示 OpenType 字体的屏幕截图。](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 有关详细信息，请参阅 [WPF 中的文档](documents-in-wpf.md)。  
  
### <a name="lightweight-text-drawing"></a>轻量文本绘制  
 您可以通过使用 <xref:System.Windows.Media.DrawingContext> 对象的 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 方法，将文本直接绘制到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的对象。 若要使用此方法，请创建一个 <xref:System.Windows.Media.FormattedText> 对象。 使用该对象可以绘制多行文本，可对文本中的每个字符单独设置格式。 <xref:System.Windows.Media.FormattedText> 对象的功能包含 Windows API 中 DrawText 标志的许多功能。 此外，<xref:System.Windows.Media.FormattedText> 对象还包含省略号支持等功能，在文本超出其边界时，会显示省略号。 下面的示例演示应用多种格式的文本，其中第二个和第三个单词应用了线性渐变。  
  
 ![使用 FormattedText 对象显示的文本](./media/typography-in-wpf/text-formatted-linear-gradient.jpg) 
  
 您可以将格式化文本转换为 <xref:System.Windows.Media.Geometry> 对象，从而允许您创建其他类型的视觉上有趣的文本。 例如，可以根据文本字符串的轮廓创建一个 <xref:System.Windows.Media.Geometry> 对象。  
  
 ![使用线性渐变画笔的文本轮廓](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 以下示例说明了几种通过修改已转换文本的笔划、填充和突出显示来创建悦目的视觉效果的方法。  
  
 ![对填充和笔画使用不同颜色的文本](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![将图像画笔应用于笔划和突出显示的文本](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 有关 <xref:System.Windows.Media.FormattedText> 对象的详细信息，请参阅[绘制格式化文本](drawing-formatted-text.md)。  
  
### <a name="advanced-text-formatting"></a>高级文本格式设置  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 文本 Api 的最高级别的功能，你可以通过使用 <xref:System.Windows.Media.TextFormatting.TextFormatter> 对象和 <xref:System.Windows.Media.TextFormatting> 命名空间中的其他类型来创建自定义文本布局。 利用 <xref:System.Windows.Media.TextFormatting.TextFormatter> 和关联的类，您可以实现自定义文本布局，该布局支持您自己定义的字符格式、段落样式、换行符规则和其他适用于国际文本的布局功能。 只有在极少数情况下才需要重写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 文本布局支持的默认实现。 但是，如果要创建文本编辑控件或应用程序，则可能需要非默认的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 实现。  
  
 与传统的文本 API 不同，<xref:System.Windows.Media.TextFormatting.TextFormatter> 通过一组回调方法与文本布局客户端进行交互。 它要求客户端在 <xref:System.Windows.Media.TextFormatting.TextSource> 类的实现中提供这些方法。 下图说明了客户端应用程序和 <xref:System.Windows.Media.TextFormatting.TextFormatter>之间的文本布局交互。  
  
 ![文本布局客户端和 TextFormatter 示意图](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 有关创建自定义文本布局的详细信息，请参阅[高级文本格式设置](advanced-text-formatting.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [ClearType 概述](cleartype-overview.md)
- [OpenType 字体功能](opentype-font-features.md)
- [绘制格式化文本](drawing-formatted-text.md)
- [高级文本格式设置](advanced-text-formatting.md)
- [Text](optimizing-performance-text.md)
- [Microsoft 版式](https://docs.microsoft.com/typography/)
