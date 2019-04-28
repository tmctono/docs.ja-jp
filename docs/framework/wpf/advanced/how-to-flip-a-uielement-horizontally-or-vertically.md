---
title: '方法: UIElement を左右または上下に反転させる'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767054"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="092e1-102">方法: UIElement を左右または上下に反転させる</span><span class="sxs-lookup"><span data-stu-id="092e1-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="092e1-103">この例は、使用する方法を示します、<xref:System.Windows.Media.ScaleTransform>反転する、<xref:System.Windows.UIElement>水平方向または垂直方向にします。</span><span class="sxs-lookup"><span data-stu-id="092e1-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="092e1-104">この例で、<xref:System.Windows.Controls.Button>コントロール (一種の<xref:System.Windows.UIElement>) を適用することで反転、<xref:System.Windows.Media.ScaleTransform>にその<xref:System.Windows.UIElement.RenderTransform%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="092e1-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="092e1-105">例</span><span class="sxs-lookup"><span data-stu-id="092e1-105">Example</span></span>  
 <span data-ttu-id="092e1-106">次の図は、反転する ボタンを示します。</span><span class="sxs-lookup"><span data-stu-id="092e1-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="092e1-107">![変換のないボタン](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="092e1-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="092e1-108">反転する UIElement</span><span class="sxs-lookup"><span data-stu-id="092e1-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="092e1-109">ボタンを作成するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="092e1-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="092e1-110">例</span><span class="sxs-lookup"><span data-stu-id="092e1-110">Example</span></span>  
 <span data-ttu-id="092e1-111">ボタンを水平方向に反転するには作成、<xref:System.Windows.Media.ScaleTransform>設定とその<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>プロパティを-1 にします。</span><span class="sxs-lookup"><span data-stu-id="092e1-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="092e1-112">適用、<xref:System.Windows.Media.ScaleTransform>をボタンの<xref:System.Windows.UIElement.RenderTransform%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="092e1-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="092e1-113">![水平方向に反転されるボタン&#40;0, 0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="092e1-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="092e1-114">ScaleTransform を適用した後、ボタン</span><span class="sxs-lookup"><span data-stu-id="092e1-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="092e1-115">例</span><span class="sxs-lookup"><span data-stu-id="092e1-115">Example</span></span>  
 <span data-ttu-id="092e1-116">前の図からわかるように、ボタンの反転がも変わりました。</span><span class="sxs-lookup"><span data-stu-id="092e1-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="092e1-117">ボタンは左下隅から反転したためです。</span><span class="sxs-lookup"><span data-stu-id="092e1-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="092e1-118">適用する場所で、ボタンを反転する、<xref:System.Windows.Media.ScaleTransform>端のない、中央にします。</span><span class="sxs-lookup"><span data-stu-id="092e1-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="092e1-119">適用する簡単な方法、<xref:System.Windows.Media.ScaleTransform>ボタン センターで、ボタンの設定には<xref:System.Windows.UIElement.RenderTransformOrigin%2A>プロパティを 0.5 0.5 です。</span><span class="sxs-lookup"><span data-stu-id="092e1-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="092e1-120">![中心の周り水平方向に反転されるボタン](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="092e1-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="092e1-121">Rendertransformorigin が 0.5 ボタン 0.5</span><span class="sxs-lookup"><span data-stu-id="092e1-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="092e1-122">例</span><span class="sxs-lookup"><span data-stu-id="092e1-122">Example</span></span>  
 <span data-ttu-id="092e1-123">ボタンを垂直方向に反転するには設定、<xref:System.Windows.Media.ScaleTransform>オブジェクトの<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>プロパティの代わりにその<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="092e1-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="092e1-124">![中心の周り垂直方向に反転されるボタン](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="092e1-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="092e1-125">垂直方向に反転したボタン</span><span class="sxs-lookup"><span data-stu-id="092e1-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="092e1-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="092e1-126">See also</span></span>

- [<span data-ttu-id="092e1-127">変換の概要</span><span class="sxs-lookup"><span data-stu-id="092e1-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
