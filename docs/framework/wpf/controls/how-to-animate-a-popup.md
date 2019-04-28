---
title: '方法: ポップアップをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911288"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="0b8b6-102">方法: ポップアップをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="0b8b6-102">How to: Animate a Popup</span></span>
<span data-ttu-id="0b8b6-103">この例は、アニメーション化する 2 つの方法を示しています、<xref:System.Windows.Controls.Primitives.Popup>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0b8b6-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b8b6-104">例</span><span class="sxs-lookup"><span data-stu-id="0b8b6-104">Example</span></span>  
 <span data-ttu-id="0b8b6-105">次の例のセット、<xref:System.Windows.Controls.Primitives.PopupAnimation>プロパティの値を<xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>、原因となる、 <xref:System.Windows.Controls.Primitives.Popup> 「スライドで表示されるときにします。</span><span class="sxs-lookup"><span data-stu-id="0b8b6-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="0b8b6-106">回転するには、 <xref:System.Windows.Controls.Primitives.Popup>、この例に割り当てます、<xref:System.Windows.Media.RotateTransform>を<xref:System.Windows.UIElement.RenderTransform%2A>プロパティを<xref:System.Windows.Controls.Canvas>の子要素は、<xref:System.Windows.Controls.Primitives.Popup>します。</span><span class="sxs-lookup"><span data-stu-id="0b8b6-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="0b8b6-107">正常に動作する変換の例を設定する必要があります、<xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="0b8b6-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="0b8b6-108">さらに、<xref:System.Windows.FrameworkElement.Margin%2A>上、<xref:System.Windows.Controls.Canvas>コンテンツが十分な領域を指定する必要があります、<xref:System.Windows.Controls.Primitives.Popup>回転します。</span><span class="sxs-lookup"><span data-stu-id="0b8b6-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="0b8b6-109">次の例は方法、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベントが発生時に、<xref:System.Windows.Controls.Button>がクリックされた、トリガー、<xref:System.Windows.Media.Animation.Storyboard>アニメーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="0b8b6-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="0b8b6-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b8b6-110">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="0b8b6-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="0b8b6-111">How-to Topics</span></span>](popup-how-to-topics.md)
- [<span data-ttu-id="0b8b6-112">ポップアップの概要</span><span class="sxs-lookup"><span data-stu-id="0b8b6-112">Popup Overview</span></span>](popup-overview.md)
