---
title: '方法: Viewbox のコンテンツに Stretch プロパティを適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 08358ea07e0c41e3b7cdf52251a3ed4296035e2d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209880"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a><span data-ttu-id="dd46a-102">方法: Viewbox のコンテンツに Stretch プロパティを適用する</span><span class="sxs-lookup"><span data-stu-id="dd46a-102">How to: Apply Stretch Properties to the Contents of a Viewbox</span></span>
## <a name="example"></a><span data-ttu-id="dd46a-103">例</span><span class="sxs-lookup"><span data-stu-id="dd46a-103">Example</span></span>  
 <span data-ttu-id="dd46a-104">この例の値を変更する方法を示しています、<xref:System.Windows.Controls.Viewbox.StretchDirection%2A>と<xref:System.Windows.Controls.Viewbox.Stretch%2A>のプロパティを<xref:System.Windows.Controls.Viewbox>します。</span><span class="sxs-lookup"><span data-stu-id="dd46a-104">This example shows how to change the value of the <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> and <xref:System.Windows.Controls.Viewbox.Stretch%2A> properties of a <xref:System.Windows.Controls.Viewbox>.</span></span>  
  
 <span data-ttu-id="dd46a-105">最初の例では[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]を定義する、<xref:System.Windows.Controls.Viewbox>要素。</span><span class="sxs-lookup"><span data-stu-id="dd46a-105">The first example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.Viewbox> element.</span></span> <span data-ttu-id="dd46a-106">割り当てます、<xref:System.Windows.FrameworkElement.MaxWidth%2A>と<xref:System.Windows.FrameworkElement.MaxHeight%2A>400 です。</span><span class="sxs-lookup"><span data-stu-id="dd46a-106">It assigns a <xref:System.Windows.FrameworkElement.MaxWidth%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> of 400.</span></span> <span data-ttu-id="dd46a-107">例のネストを<xref:System.Windows.Controls.Image>内の要素、<xref:System.Windows.Controls.Viewbox>します。</span><span class="sxs-lookup"><span data-stu-id="dd46a-107">The example nests an <xref:System.Windows.Controls.Image> element within the <xref:System.Windows.Controls.Viewbox>.</span></span> <span data-ttu-id="dd46a-108"><xref:System.Windows.Controls.Button> プロパティの値に対応する要素、<xref:System.Windows.Controls.Viewbox.Stretch%2A>と<xref:System.Windows.Controls.StretchDirection>列挙体は、入れ子になったの伸縮動作を操作<xref:System.Windows.Controls.Image>します。</span><span class="sxs-lookup"><span data-stu-id="dd46a-108"><xref:System.Windows.Controls.Button> elements that correspond to the property values for the <xref:System.Windows.Controls.Viewbox.Stretch%2A> and <xref:System.Windows.Controls.StretchDirection> enumerations manipulate the stretching behavior of the nested <xref:System.Windows.Controls.Image>.</span></span>  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="dd46a-109">次のコード ビハインド ファイル ハンドル、 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベントを以前[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]例で定義します。</span><span class="sxs-lookup"><span data-stu-id="dd46a-109">The following code-behind file handles the <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events that the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example defines.</span></span>  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="dd46a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd46a-110">See also</span></span>

- <xref:System.Windows.Controls.Viewbox>
- <xref:System.Windows.Media.Stretch>
- <xref:System.Windows.Controls.StretchDirection>
