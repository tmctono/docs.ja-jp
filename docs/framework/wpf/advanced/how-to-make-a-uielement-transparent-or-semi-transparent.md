---
title: '方法: UIElement を透明または半透明にする'
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942871"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="0df1b-102">方法: UIElement を透明または半透明にする</span><span class="sxs-lookup"><span data-stu-id="0df1b-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="0df1b-103">この例では、作成、<xref:System.Windows.UIElement>透明または半透明にします。</span><span class="sxs-lookup"><span data-stu-id="0df1b-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="0df1b-104">設定する要素を透明または半透明にするその<xref:System.Windows.UIElement.Opacity%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0df1b-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="0df1b-105">値`0.0`の値の中に、完全に透明な要素は、`1.0`要素を完全に不透明になります。</span><span class="sxs-lookup"><span data-stu-id="0df1b-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="0df1b-106">値`0.5`、不透明で、要素を 50% になります。</span><span class="sxs-lookup"><span data-stu-id="0df1b-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="0df1b-107">要素の<xref:System.Windows.UIElement.Opacity%2A>に設定されている`1.0`既定。</span><span class="sxs-lookup"><span data-stu-id="0df1b-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0df1b-108">例</span><span class="sxs-lookup"><span data-stu-id="0df1b-108">Example</span></span>  
 <span data-ttu-id="0df1b-109">次の例のセット、<xref:System.Windows.UIElement.Opacity%2A>するボタンの`0.25`、作成し、その内容 (この例では、ボタンのテキスト) では 25% 不透明です。</span><span class="sxs-lookup"><span data-stu-id="0df1b-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="0df1b-110">要素の内容がある独自場合<xref:System.Windows.UIElement.Opacity%2A>設定、それらの値を含んでいる要素に対して乗算<xref:System.Windows.UIElement.Opacity%2A>します。</span><span class="sxs-lookup"><span data-stu-id="0df1b-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="0df1b-111">次の例では、ボタンの<xref:System.Windows.UIElement.Opacity%2A>に`0.25`、および<xref:System.Windows.UIElement.Opacity%2A>の<xref:System.Windows.Controls.Image>をボタンに含まれるコントロール`0.5`します。</span><span class="sxs-lookup"><span data-stu-id="0df1b-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="0df1b-112">その結果、イメージには、12.5% 不透明が表示されます。0.25 \* 0.5 = 0.125.</span><span class="sxs-lookup"><span data-stu-id="0df1b-112">As a result, the image appears 12.5% opaque: 0.25 \* 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="0df1b-113">要素の不透明度を制御するもう 1 つの方法は、の不透明度を設定するのには、<xref:System.Windows.Media.Brush>要素を描画します。</span><span class="sxs-lookup"><span data-stu-id="0df1b-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="0df1b-114">このアプローチは選択的に、要素の各部分の不透明度を変更することができ、要素を使用してパフォーマンスのメリットが得<xref:System.Windows.UIElement.Opacity%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0df1b-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="0df1b-115">次の例のセット、<xref:System.Windows.Media.Brush.Opacity%2A>の<xref:System.Windows.Media.SolidColorBrush>ボタンの描画に使用される<xref:System.Windows.Controls.Control.Background%2A>に設定されている`0.25`します。</span><span class="sxs-lookup"><span data-stu-id="0df1b-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="0df1b-116">その結果、ブラシの背景が 25% 不透明でが不透明度 100% のままの内容 (ボタンのテキスト)。</span><span class="sxs-lookup"><span data-stu-id="0df1b-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="0df1b-117">ブラシ内の個々 の色の不透明度を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="0df1b-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="0df1b-118">色とブラシの詳細については、次を参照してください。[純色およびグラデーション概要](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="0df1b-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="0df1b-119">要素の不透明度をアニメーション化する方法を示す例は、次を参照してください。[要素またはブラシの不透明度をアニメーション化する](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md)します。</span><span class="sxs-lookup"><span data-stu-id="0df1b-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
