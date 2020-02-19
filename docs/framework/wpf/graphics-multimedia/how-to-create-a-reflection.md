---
title: '方法 : 反射を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 8a5ed345c0aa25312bd74799264e1f66ab4554e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452059"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="0c8e6-102">方法 : 反射を作成する</span><span class="sxs-lookup"><span data-stu-id="0c8e6-102">How to: Create a Reflection</span></span>
<span data-ttu-id="0c8e6-103">この例では、<xref:System.Windows.Media.VisualBrush> を使用してリフレクションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0c8e6-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="0c8e6-104"><xref:System.Windows.Media.VisualBrush> は既存のビジュアルを表示できるため、この機能を使用して、反射や拡大などの興味深い視覚効果を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="0c8e6-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c8e6-105">例</span><span class="sxs-lookup"><span data-stu-id="0c8e6-105">Example</span></span>  
 <span data-ttu-id="0c8e6-106">次の例では、<xref:System.Windows.Media.VisualBrush> を使用して、複数の要素を含む <xref:System.Windows.Controls.Border> のリフレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c8e6-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="0c8e6-107">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c8e6-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="0c8e6-108">![反映された Visual オブジェクト](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="0c8e6-108">![A reflected Visual object](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="0c8e6-109">反映された Visual オブジェクト</span><span class="sxs-lookup"><span data-stu-id="0c8e6-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="0c8e6-110">画面の一部を拡大する方法と、反射を作成する方法を示す例を含む完全なサンプルについては、「 [Visualbrush sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c8e6-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8e6-111">参照</span><span class="sxs-lookup"><span data-stu-id="0c8e6-111">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="0c8e6-112">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="0c8e6-112">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
