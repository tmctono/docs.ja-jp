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
ms.openlocfilehash: 52b9b99b0af38d797e4a3c98dc0979211c930c1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923378"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="baa79-102">方法: ビジュアル内のジオメトリのヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="baa79-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="baa79-103">この例では、1つ<xref:System.Windows.Media.Geometry>以上のオブジェクトで構成されるビジュアルオブジェクトに対してヒットテストを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="baa79-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baa79-104">例</span><span class="sxs-lookup"><span data-stu-id="baa79-104">Example</span></span>  
 <span data-ttu-id="baa79-105">次の例は、 <xref:System.Windows.Media.DrawingGroup> <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>メソッドを使用するビジュアルオブジェクトからを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="baa79-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="baa79-106">次に、 <xref:System.Windows.Media.DrawingGroup>内の各描画のレンダリングされたコンテンツに対してヒットテストが実行され、ヒットしたジオメトリが特定されます。</span><span class="sxs-lookup"><span data-stu-id="baa79-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baa79-107">ほとんどの場合、 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>メソッドを使用して、ビジュアルの描画されたコンテンツのいずれかにポイントが交差するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="baa79-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="baa79-108">メソッドは、指定されたまたは<xref:System.Windows.Media.Geometry>を使用してヒットテストを<xref:System.Windows.Point>実行できるようにする、オーバーロードされたメソッドです。 <xref:System.Windows.Media.Geometry.FillContains%2A></span><span class="sxs-lookup"><span data-stu-id="baa79-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="baa79-109">ジオメトリに線が付いている場合は、塗りつぶしの境界の外側までストロークを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="baa79-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="baa79-110">そのような場合は、に<xref:System.Windows.Media.Geometry.StrokeContains%2A> <xref:System.Windows.Media.Geometry.FillContains%2A>加えて、を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="baa79-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="baa79-111">また、ベジエフラット化<xref:System.Windows.Media.ToleranceType>の目的で使用されるを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="baa79-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baa79-112">このサンプルでは、ジオメトリに適用される可能性のある変換やクリッピングは考慮していません。</span><span class="sxs-lookup"><span data-stu-id="baa79-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="baa79-113">また、スタイルが設定されたコントロールには直接関連付けられた描画がないので、このサンプルはスタイルが設定されたコントロールに対しては機能しません。</span><span class="sxs-lookup"><span data-stu-id="baa79-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa79-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="baa79-114">See also</span></span>

- [<span data-ttu-id="baa79-115">ビジュアル層でのヒット テスト</span><span class="sxs-lookup"><span data-stu-id="baa79-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="baa79-116">パラメーターとしてジオメトリを使用してヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="baa79-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
