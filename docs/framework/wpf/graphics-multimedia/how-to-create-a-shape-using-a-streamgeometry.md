---
title: '方法: StreamGeometry を使用して図形を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: ce2097568349ad376540163f5fe05d6a3e5b0643
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348026"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="c3acb-102">方法: StreamGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="c3acb-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="c3acb-103"><xref:System.Windows.Media.StreamGeometry> 軽量の代わりには、<xref:System.Windows.Media.PathGeometry>幾何学的図形を作成するためです。</span><span class="sxs-lookup"><span data-stu-id="c3acb-103"><xref:System.Windows.Media.StreamGeometry> is lightweight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="c3acb-104">使用して、<xref:System.Windows.Media.StreamGeometry>複雑なジオメトリを記述する必要がある場合がデータ バインディング、アニメーション、または変更をサポートするオーバーヘッドを作成したくないです。</span><span class="sxs-lookup"><span data-stu-id="c3acb-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="c3acb-105">など、効率的であるため、<xref:System.Windows.Media.StreamGeometry>クラスは、装飾の記述に適しています。</span><span class="sxs-lookup"><span data-stu-id="c3acb-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3acb-106">例</span><span class="sxs-lookup"><span data-stu-id="c3acb-106">Example</span></span>  
 <span data-ttu-id="c3acb-107">次の例では、属性構文を使用して、三角形を作成する<xref:System.Windows.Media.StreamGeometry>で[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c3acb-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="c3acb-108">詳細については<xref:System.Windows.Media.StreamGeometry>属性構文を参照してください、[パス マークアップ構文](path-markup-syntax.md)ページ。</span><span class="sxs-lookup"><span data-stu-id="c3acb-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3acb-109">例</span><span class="sxs-lookup"><span data-stu-id="c3acb-109">Example</span></span>  
 <span data-ttu-id="c3acb-110">次の例では、<xref:System.Windows.Media.StreamGeometry>コードで三角形を定義します。</span><span class="sxs-lookup"><span data-stu-id="c3acb-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="c3acb-111">最初に、例、<xref:System.Windows.Media.StreamGeometry>を取得し、<xref:System.Windows.Media.StreamGeometryContext>それを使って、三角形の説明をします。</span><span class="sxs-lookup"><span data-stu-id="c3acb-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="c3acb-112">例</span><span class="sxs-lookup"><span data-stu-id="c3acb-112">Example</span></span>  
 <span data-ttu-id="c3acb-113">次の例は、使用するメソッドを作成、<xref:System.Windows.Media.StreamGeometry>と<xref:System.Windows.Media.StreamGeometryContext>を指定したパラメーターに基づいて、幾何学図形を定義します。</span><span class="sxs-lookup"><span data-stu-id="c3acb-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c3acb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3acb-114">See also</span></span>

- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [<span data-ttu-id="c3acb-115">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="c3acb-115">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [<span data-ttu-id="c3acb-116">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="c3acb-116">Geometry Overview</span></span>](geometry-overview.md)
