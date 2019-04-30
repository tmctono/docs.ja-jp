---
title: '方法: ビジュアル内のジオメトリのヒット テストを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 87b626e575d889447ef061d1ed62ef28efe5dfeb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947343"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="1ae73-102">方法: ビジュアル内のジオメトリのヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="1ae73-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="1ae73-103">この例は、1 つまたは複数で構成されるビジュアル オブジェクトに対してヒット テストを実行する方法を示しています。<xref:System.Windows.Media.Geometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ae73-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ae73-104">例</span><span class="sxs-lookup"><span data-stu-id="1ae73-104">Example</span></span>  
 <span data-ttu-id="1ae73-105">次の例は、取得する方法を示します、<xref:System.Windows.Media.DrawingGroup>を使用するビジュアル オブジェクトから、<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="1ae73-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="1ae73-106">各描画の描画されるコンテンツのヒット テストが実行、<xref:System.Windows.Media.DrawingGroup>をヒットしたジオメトリを判断します。</span><span class="sxs-lookup"><span data-stu-id="1ae73-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ae73-107">ほとんどの場合、使用すると、<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>ポイントと交差するビジュアルの表示内容にするかどうかを判断するメソッド。</span><span class="sxs-lookup"><span data-stu-id="1ae73-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="1ae73-108"><xref:System.Windows.Media.Geometry.FillContains%2A>メソッドがオーバー ロードされたメソッドを使用すると、指定されたを使用してヒット テストを<xref:System.Windows.Point>または<xref:System.Windows.Media.Geometry>します。</span><span class="sxs-lookup"><span data-stu-id="1ae73-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="1ae73-109">ジオメトリに線が付いている場合は、塗りつぶしの境界の外側までストロークを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="1ae73-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="1ae73-110">呼び出すしたい場合は、<xref:System.Windows.Media.Geometry.StrokeContains%2A>に加えて<xref:System.Windows.Media.Geometry.FillContains%2A>します。</span><span class="sxs-lookup"><span data-stu-id="1ae73-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="1ae73-111">提供することも、<xref:System.Windows.Media.ToleranceType>ベジエ平坦化のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ae73-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ae73-112">このサンプルでは、ジオメトリに適用される可能性のある変換やクリッピングは考慮していません。</span><span class="sxs-lookup"><span data-stu-id="1ae73-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="1ae73-113">また、スタイルが設定されたコントロールには直接関連付けられた描画がないので、このサンプルはスタイルが設定されたコントロールに対しては機能しません。</span><span class="sxs-lookup"><span data-stu-id="1ae73-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae73-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ae73-114">See also</span></span>

- [<span data-ttu-id="1ae73-115">ビジュアル層でのヒット テスト</span><span class="sxs-lookup"><span data-stu-id="1ae73-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="1ae73-116">パラメーターとしてジオメトリを使用してヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="1ae73-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
