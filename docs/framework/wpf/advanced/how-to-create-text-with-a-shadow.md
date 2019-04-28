---
title: '方法: 影付きテキストを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: a2225e297dbc0b5f9d49799cb34eb5539746e62e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776817"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="5be44-102">方法: 影付きテキストを作成する</span><span class="sxs-lookup"><span data-stu-id="5be44-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="5be44-103">このセクションの例で、表示されるテキストに影を付ける方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="5be44-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5be44-104">例</span><span class="sxs-lookup"><span data-stu-id="5be44-104">Example</span></span>  
 <span data-ttu-id="5be44-105"><xref:System.Windows.Media.Effects.DropShadowEffect>オブジェクトでは、さまざまなドロップ シャドウ効果を作成できます。[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5be44-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="5be44-106">テキストにドロップ シャドウ効果を適用した例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="5be44-107">この場合、影はソフト シャドウです。つまり、影の色がぼやけています。</span><span class="sxs-lookup"><span data-stu-id="5be44-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![テキストの影のぼかしを&#61;0.25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 <span data-ttu-id="5be44-109">設定して影の幅を制御することができます、<xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5be44-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="5be44-110">値`4.0`4 ピクセルの影の幅を示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="5be44-111">ぼかしを制御する、または変更することで、シャドウのぼかし、<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5be44-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="5be44-112">値`0.0`ぼかしはありません。</span><span class="sxs-lookup"><span data-stu-id="5be44-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="5be44-113">ソフト シャドウを付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="5be44-114">これらのシャドウ効果を通過しない、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]テキスト レンダリング パイプライン。</span><span class="sxs-lookup"><span data-stu-id="5be44-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="5be44-115">結果として、これらの効果の利用時、ClearType が無効になります。</span><span class="sxs-lookup"><span data-stu-id="5be44-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="5be44-116">テキストにハード シャドウ効果を適用した例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="5be44-117">この場合、影はぼかされません。</span><span class="sxs-lookup"><span data-stu-id="5be44-117">In this case, the shadow is not blurred.</span></span>  
  
 ![テキストの影のぼかしを&#61;0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 <span data-ttu-id="5be44-119">ハード シャドウを作成するには設定して、<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>プロパティを`0.0`、ぼかし効果が使用されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="5be44-120">影の方向を制御するには変更することによって、<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5be44-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="5be44-121">このプロパティの方向性のある値を設定間の角度に`0`と`360`します。</span><span class="sxs-lookup"><span data-stu-id="5be44-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="5be44-122">次の図の方向値、<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="5be44-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![シャドウの DropShadow 度の設定](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="5be44-124">ハード シャドウを付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="5be44-125">ぼかし効果を使用する</span><span class="sxs-lookup"><span data-stu-id="5be44-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="5be44-126">A<xref:System.Windows.Media.Effects.BlurBitmapEffect>テキスト オブジェクトの後ろに配置できる影のような効果を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5be44-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="5be44-127">テキストに適用されたぼかしビットマップ効果は、全方向に均等にテキストをぼかします。</span><span class="sxs-lookup"><span data-stu-id="5be44-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="5be44-128">テキストにぼかし効果が適用されている例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![BlurBitmapEffect を使用するテキスト シャドウ](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="5be44-130">ぼかし効果を付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="5be44-131">TranslateTransform を使用する</span><span class="sxs-lookup"><span data-stu-id="5be44-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="5be44-132">A<xref:System.Windows.Media.TranslateTransform>テキスト オブジェクトの後ろに配置できる影のような効果を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5be44-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="5be44-133">次のコード例では、<xref:System.Windows.Media.TranslateTransform>テキストのオフセット。</span><span class="sxs-lookup"><span data-stu-id="5be44-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="5be44-134">この例では、メインのテキストの下にわずかに中心をずらしたコピーが付き、影のような効果を作っています。</span><span class="sxs-lookup"><span data-stu-id="5be44-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![TranslateTransform を使用するテキスト シャドウ](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 <span data-ttu-id="5be44-136">TranslateTransform を利用して影のような効果を付ける方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="5be44-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
