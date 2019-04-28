---
title: '方法: プロパティ値が変化したときにアニメーションをトリガーする'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769305"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="32137-102">方法: プロパティ値が変化したときにアニメーションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="32137-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="32137-103">この例は、使用する方法を示します、<xref:System.Windows.Trigger>を開始する、<xref:System.Windows.Media.Animation.Storyboard>プロパティ値が変更されたとき。</span><span class="sxs-lookup"><span data-stu-id="32137-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="32137-104">使用することができます、<xref:System.Windows.Trigger>内で、 <xref:System.Windows.Style>、 <xref:System.Windows.Controls.ControlTemplate>、または<xref:System.Windows.DataTemplate>します。</span><span class="sxs-lookup"><span data-stu-id="32137-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32137-105">例</span><span class="sxs-lookup"><span data-stu-id="32137-105">Example</span></span>  
 <span data-ttu-id="32137-106">次の例では、<xref:System.Windows.Trigger>をアニメーション化する、<xref:System.Windows.UIElement.Opacity%2A>の<xref:System.Windows.Controls.Button>ときにその<xref:System.Windows.UIElement.IsMouseOver%2A>プロパティになります`true`します。</span><span class="sxs-lookup"><span data-stu-id="32137-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="32137-107">プロパティによって適用されるアニメーション<xref:System.Windows.Trigger>オブジェクトよりもさらに複雑な方法で動作しますが<xref:System.Windows.EventTrigger>アニメーションまたはアニメーションの開始を使用して<xref:System.Windows.Media.Animation.Storyboard>メソッド。</span><span class="sxs-lookup"><span data-stu-id="32137-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="32137-108">「ハンドオフ」アニメーションによって他の定義、<xref:System.Windows.Trigger>オブジェクトで、compose を<xref:System.Windows.EventTrigger>メソッドによってトリガーされるアニメーションです。</span><span class="sxs-lookup"><span data-stu-id="32137-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32137-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="32137-109">See also</span></span>

- <xref:System.Windows.Trigger>
- [<span data-ttu-id="32137-110">プロパティ アニメーションの手法の概要</span><span class="sxs-lookup"><span data-stu-id="32137-110">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="32137-111">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="32137-111">Storyboards Overview</span></span>](storyboards-overview.md)
