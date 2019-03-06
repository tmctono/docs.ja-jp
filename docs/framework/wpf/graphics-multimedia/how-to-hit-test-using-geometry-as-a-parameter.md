---
title: '方法: パラメーターとしてジオメトリを使用してヒット テストを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 15a33d05cb3ca4fd40f04170bd1756e466631275
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366362"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="5c52f-102">方法: パラメーターとしてジオメトリを使用してヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="5c52f-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="5c52f-103">この例を使用して、ビジュアル オブジェクトに対してヒット テストを実行する方法を示しています、<xref:System.Windows.Media.Geometry>ヒット テスト パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5c52f-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c52f-104">例</span><span class="sxs-lookup"><span data-stu-id="5c52f-104">Example</span></span>  
 <span data-ttu-id="5c52f-105">次の例を使用してヒット テストを設定する方法を示しています。<xref:System.Windows.Media.GeometryHitTestParameters>の、<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="5c52f-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="5c52f-106"><xref:System.Windows.Point>に渡される値、`OnMouseDown`メソッドの使用を作成、<xref:System.Windows.Media.Geometry>ヒット テストの範囲を拡張するためにオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5c52f-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="5c52f-107"><xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A>プロパティの<xref:System.Windows.Media.GeometryHitTestResult>を使用するヒット テストの結果に関する情報を提供します、<xref:System.Windows.Media.Geometry>ヒット テスト パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5c52f-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="5c52f-108">ヒット テストのジオメトリ (青い円) と対象のビジュアル オブジェクト (赤い正方形) の描画されるコンテンツとの関係を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="5c52f-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 <span data-ttu-id="5c52f-109">![ヒット テストで使用される IntersectionDetail のダイアグラム](./media/intersectiondetail01.png "IntersectionDetail01")</span><span class="sxs-lookup"><span data-stu-id="5c52f-109">![Diagram of IntersectionDetail used in hit testing](./media/intersectiondetail01.png "IntersectionDetail01")</span></span>  
<span data-ttu-id="5c52f-110">ヒット テストのジオメトリと対象のビジュアル オブジェクトの交差部分</span><span class="sxs-lookup"><span data-stu-id="5c52f-110">Intersection between hit test geometry and target visual object</span></span>  
  
 <span data-ttu-id="5c52f-111">次の例は、ヒット テスト コールバックを実装する方法を示しています。 ときに、<xref:System.Windows.Media.Geometry>ヒット テスト パラメーターとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c52f-111">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="5c52f-112">`result`にパラメーターをキャスト、<xref:System.Windows.Media.GeometryHitTestResult>の値を取得するために、<xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5c52f-112">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="5c52f-113">プロパティの値を使用するかどうか、<xref:System.Windows.Media.Geometry>ヒット テスト パラメーター完全または部分的に含まれるヒット テスト対象の表示内容。</span><span class="sxs-lookup"><span data-stu-id="5c52f-113">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="5c52f-114">ここに示すサンプル コードでは、完全に対象の境界内に含まれるビジュアルについてのみ、ヒット テストの結果をリストに追加しています。</span><span class="sxs-lookup"><span data-stu-id="5c52f-114">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="5c52f-115"><xref:System.Windows.Media.HitTestResult> 、Intersectiondetail がときに、コールバックを呼び出すことはできません<xref:System.Windows.Media.IntersectionDetail.Empty>します。</span><span class="sxs-lookup"><span data-stu-id="5c52f-115">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c52f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c52f-116">See also</span></span>
- [<span data-ttu-id="5c52f-117">ビジュアル層でのヒット テスト</span><span class="sxs-lookup"><span data-stu-id="5c52f-117">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="5c52f-118">ビジュアル内のジオメトリのヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="5c52f-118">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
