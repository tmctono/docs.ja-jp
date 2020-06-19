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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348026"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="4fca6-102">方法: StreamGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="4fca6-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="4fca6-103"><xref:System.Windows.Media.StreamGeometry> は、幾何学図形を作成するための <xref:System.Windows.Media.PathGeometry> に代わる軽量の手段です。</span><span class="sxs-lookup"><span data-stu-id="4fca6-103"><xref:System.Windows.Media.StreamGeometry> is lightweight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="4fca6-104">複雑なジオメトリを記述する必要があるが、データ バインディング、アニメーション、または変更をサポートするオーバーヘッドが望ましくない場合は、<xref:System.Windows.Media.StreamGeometry> を使用します。</span><span class="sxs-lookup"><span data-stu-id="4fca6-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="4fca6-105">たとえば、<xref:System.Windows.Media.StreamGeometry> クラスは効率的であるため、装飾の記述に適しています。</span><span class="sxs-lookup"><span data-stu-id="4fca6-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fca6-106">例</span><span class="sxs-lookup"><span data-stu-id="4fca6-106">Example</span></span>  
 <span data-ttu-id="4fca6-107">次の例では、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] で属性構文の使用によって三角形の <xref:System.Windows.Media.StreamGeometry> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4fca6-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="4fca6-108"><xref:System.Windows.Media.StreamGeometry> 属性構文の詳細については、「[パス マークアップ構文](path-markup-syntax.md)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fca6-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fca6-109">例</span><span class="sxs-lookup"><span data-stu-id="4fca6-109">Example</span></span>  
 <span data-ttu-id="4fca6-110">次の例では、コードで <xref:System.Windows.Media.StreamGeometry> を使用して三角形が定義されます。</span><span class="sxs-lookup"><span data-stu-id="4fca6-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="4fca6-111">この例ではまず、<xref:System.Windows.Media.StreamGeometry> が作成され、次に <xref:System.Windows.Media.StreamGeometryContext> が取得され、それを使用して三角形が記述されます。</span><span class="sxs-lookup"><span data-stu-id="4fca6-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="4fca6-112">例</span><span class="sxs-lookup"><span data-stu-id="4fca6-112">Example</span></span>  
 <span data-ttu-id="4fca6-113">次の例では、<xref:System.Windows.Media.StreamGeometry> と <xref:System.Windows.Media.StreamGeometryContext> を使用するメソッドが作成され、指定されたパラメーターに基づいて幾何学図形が定義されます。</span><span class="sxs-lookup"><span data-stu-id="4fca6-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4fca6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fca6-114">See also</span></span>

- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [<span data-ttu-id="4fca6-115">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="4fca6-115">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [<span data-ttu-id="4fca6-116">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="4fca6-116">Geometry Overview</span></span>](geometry-overview.md)
