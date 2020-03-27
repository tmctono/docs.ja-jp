---
title: '方法 : ポップアップのカスタム位置を指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: ea8d73c51dd018608b95104f00bf341ff434225c
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344951"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="dece9-102">方法 : ポップアップのカスタム位置を指定する</span><span class="sxs-lookup"><span data-stu-id="dece9-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="dece9-103">この例では、プロパティが に設定されているときに<xref:System.Windows.Controls.Primitives.Popup>、コントロールの<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>カスタム位置を指定<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dece9-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dece9-104">例</span><span class="sxs-lookup"><span data-stu-id="dece9-104">Example</span></span>  
 <span data-ttu-id="dece9-105">プロパティが<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>に<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>設定されている場合、<xref:System.Windows.Controls.Primitives.Popup>デリゲートの定義済みインスタンスが<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dece9-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="dece9-106">このデリゲートは、ターゲット領域の左上隅との左上隅を基準にした、指定できるポイントのセットを返します<xref:System.Windows.Controls.Primitives.Popup>。</span><span class="sxs-lookup"><span data-stu-id="dece9-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="dece9-107">配置<xref:System.Windows.Controls.Primitives.Popup>は、最適な可視性を提供するポイントで行われます。</span><span class="sxs-lookup"><span data-stu-id="dece9-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="dece9-108">プロパティを に設定して、 の<xref:System.Windows.Controls.Primitives.Popup>位置を定義する方法<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>を次<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>の例に示します。</span><span class="sxs-lookup"><span data-stu-id="dece9-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="dece9-109">また、 デリゲートを作成して割り<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>当てる方法も示しています<xref:System.Windows.Controls.Primitives.Popup>。</span><span class="sxs-lookup"><span data-stu-id="dece9-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="dece9-110">コールバック デリゲートは<xref:System.Windows.Controls.Primitives.CustomPopupPlacement>2 つのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="dece9-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="dece9-111">が最初<xref:System.Windows.Controls.Primitives.Popup>の位置の画面エッジによって隠されている場合、は<xref:System.Windows.Controls.Primitives.Popup>2 番目の位置に配置されます。</span><span class="sxs-lookup"><span data-stu-id="dece9-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="dece9-112">完全なサンプルについては、「[ポップアップ配置のサンプル](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dece9-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dece9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="dece9-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="dece9-114">ポップアップの概要</span><span class="sxs-lookup"><span data-stu-id="dece9-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="dece9-115">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="dece9-115">How-to Topics</span></span>](popup-how-to-topics.md)
