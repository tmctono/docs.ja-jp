---
title: '方法: ポップアップのカスタム位置を指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: dc516f0eb1cfcbac6662497eb4019041eefec2a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200585"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="d4033-102">方法: ポップアップのカスタム位置を指定する</span><span class="sxs-lookup"><span data-stu-id="d4033-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="d4033-103">この例のカスタム位置を指定する方法を示しています、<xref:System.Windows.Controls.Primitives.Popup>タイミングを制御、<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>プロパティに設定されて<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>します。</span><span class="sxs-lookup"><span data-stu-id="d4033-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4033-104">例</span><span class="sxs-lookup"><span data-stu-id="d4033-104">Example</span></span>  
 <span data-ttu-id="d4033-105">ときに、<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>プロパティに設定されて<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>、<xref:System.Windows.Controls.Primitives.Popup>の定義済みのインスタンスを呼び出し、<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>を委任します。</span><span class="sxs-lookup"><span data-stu-id="d4033-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="d4033-106">このデリゲートは、ターゲット領域の左上隅との左上隅に対して相対的である可能性のあるポイントのセットを返します、<xref:System.Windows.Controls.Primitives.Popup>します。</span><span class="sxs-lookup"><span data-stu-id="d4033-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="d4033-107"><xref:System.Windows.Controls.Primitives.Popup>最適な可視性を提供する時点で配置が発生します。</span><span class="sxs-lookup"><span data-stu-id="d4033-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="d4033-108">次の例の位置を定義する方法を示しています、<xref:System.Windows.Controls.Primitives.Popup>を設定して、<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>プロパティを<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>します。</span><span class="sxs-lookup"><span data-stu-id="d4033-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="d4033-109">作成して割り当てる方法も示します、<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>デリゲートを配置するために、<xref:System.Windows.Controls.Primitives.Popup>します。</span><span class="sxs-lookup"><span data-stu-id="d4033-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="d4033-110">2 つのコールバック デリゲートを返します<xref:System.Windows.Controls.Primitives.CustomPopupPlacement>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d4033-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="d4033-111">場合、<xref:System.Windows.Controls.Primitives.Popup>は、最初の位置にある画面の端で非表示、<xref:System.Windows.Controls.Primitives.Popup>が 2 番目の位置に配置されます。</span><span class="sxs-lookup"><span data-stu-id="d4033-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="d4033-112">サンプル全体については、次を参照してください。[ポップアップの配置のサンプル](https://go.microsoft.com/fwlink/?LinkID=160032)します。</span><span class="sxs-lookup"><span data-stu-id="d4033-112">For the complete sample, see [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4033-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4033-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="d4033-114">ポップアップの概要</span><span class="sxs-lookup"><span data-stu-id="d4033-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="d4033-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="d4033-115">How-to Topics</span></span>](popup-how-to-topics.md)
