---
title: '方法 : 影付きテキストを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: c3e8135372ce4a092552c812cd971cb70bc49bf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186842"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="720e4-102">方法 : 影付きテキストを作成する</span><span class="sxs-lookup"><span data-stu-id="720e4-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="720e4-103">このセクションの例で、表示されるテキストに影を付ける方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="720e4-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="720e4-104">例</span><span class="sxs-lookup"><span data-stu-id="720e4-104">Example</span></span>  
 <span data-ttu-id="720e4-105">オブジェクト<xref:System.Windows.Media.Effects.DropShadowEffect>を使用すると、オブジェクトに対してさまざまなドロップ シャドウ[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]効果を作成できます。</span><span class="sxs-lookup"><span data-stu-id="720e4-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="720e4-106">テキストにドロップ シャドウ効果を適用した例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="720e4-107">この場合、影はソフト シャドウです。つまり、影の色がぼやけています。</span><span class="sxs-lookup"><span data-stu-id="720e4-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![ソフトネス&#61;のテキストシャドウ 0.25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 <span data-ttu-id="720e4-109">プロパティを設定すると、影の幅を<xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>制御できます。</span><span class="sxs-lookup"><span data-stu-id="720e4-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="720e4-110">の値は`4.0`、4 ピクセルのシャドウ幅を示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="720e4-111">プロパティを変更することで、影の柔らかさやぼかしを<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>コントロールできます。</span><span class="sxs-lookup"><span data-stu-id="720e4-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="720e4-112">の値は`0.0`ぼかしがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="720e4-113">ソフト シャドウを付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="720e4-114">これらのシャドウ効果は、テキスト レンダリング[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]パイプラインを通過しません。</span><span class="sxs-lookup"><span data-stu-id="720e4-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="720e4-115">結果として、これらの効果の利用時、ClearType が無効になります。</span><span class="sxs-lookup"><span data-stu-id="720e4-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="720e4-116">テキストにハード シャドウ効果を適用した例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="720e4-117">この場合、影はぼかされません。</span><span class="sxs-lookup"><span data-stu-id="720e4-117">In this case, the shadow is not blurred.</span></span>  
  
 ![ソフトネス&#61; 0 のテキストシャドウ](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 <span data-ttu-id="720e4-119">プロパティを<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>`0.0`に設定して、ハード シャドウを作成できます。</span><span class="sxs-lookup"><span data-stu-id="720e4-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="720e4-120">プロパティを変更することで、影の方向を<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>制御できます。</span><span class="sxs-lookup"><span data-stu-id="720e4-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="720e4-121">このプロパティの方向値を と の`0``360`間の程度に設定します。</span><span class="sxs-lookup"><span data-stu-id="720e4-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="720e4-122">次の図は、プロパティ設定の方向<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>値を示しています。</span><span class="sxs-lookup"><span data-stu-id="720e4-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![シャドウの DropShadow 度の設定](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="720e4-124">ハード シャドウを付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="720e4-125">ぼかし効果を使用する</span><span class="sxs-lookup"><span data-stu-id="720e4-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="720e4-126">A<xref:System.Windows.Media.Effects.BlurBitmapEffect>を使用すると、テキスト オブジェクトの背後に配置できる影のような効果を作成できます。</span><span class="sxs-lookup"><span data-stu-id="720e4-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="720e4-127">テキストに適用されたぼかしビットマップ効果は、全方向に均等にテキストをぼかします。</span><span class="sxs-lookup"><span data-stu-id="720e4-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="720e4-128">テキストにぼかし効果が適用されている例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![BlurBitmapEffect を使用するテキスト シャドウ](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="720e4-130">ぼかし効果を付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="720e4-131">TranslateTransform を使用する</span><span class="sxs-lookup"><span data-stu-id="720e4-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="720e4-132">A<xref:System.Windows.Media.TranslateTransform>を使用すると、テキスト オブジェクトの背後に配置できる影のような効果を作成できます。</span><span class="sxs-lookup"><span data-stu-id="720e4-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="720e4-133">次のコード例では、<xref:System.Windows.Media.TranslateTransform>を使用してテキストをオフセットします。</span><span class="sxs-lookup"><span data-stu-id="720e4-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="720e4-134">この例では、メインのテキストの下にわずかに中心をずらしたコピーが付き、影のような効果を作っています。</span><span class="sxs-lookup"><span data-stu-id="720e4-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![TranslateTransform を使用するテキスト シャドウ](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 <span data-ttu-id="720e4-136">TranslateTransform を利用して影のような効果を付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="720e4-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
