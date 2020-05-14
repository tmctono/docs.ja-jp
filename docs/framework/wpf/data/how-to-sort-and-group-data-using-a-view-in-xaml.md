---
title: '方法: XAML でビューを使用してデータの並べ替えおよびグループ化を行う'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460117"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="7dcbe-102">方法: XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="7dcbe-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="7dcbe-103">この例では、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] でデータ コレクションのビューを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7dcbe-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="7dcbe-104">ビューでは、グループ化、並べ替え、フィルター処理、現在の項目の概念などの機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7dcbe-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dcbe-105">例</span><span class="sxs-lookup"><span data-stu-id="7dcbe-105">Example</span></span>  
 <span data-ttu-id="7dcbe-106">次の例では、*places* という名前の静的リソースは *Place* オブジェクトのコレクションとして定義されており、各 *Place* オブジェクトは市の名前と州で構成されます。</span><span class="sxs-lookup"><span data-stu-id="7dcbe-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="7dcbe-107">プレフィックス *src* は、データソース *Places* が定義されている名前空間にマップされています。</span><span class="sxs-lookup"><span data-stu-id="7dcbe-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="7dcbe-108">プレフィックス *scm* は `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` にマップされ、*dat* は `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` にマップされています。</span><span class="sxs-lookup"><span data-stu-id="7dcbe-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="7dcbe-109">次の例では、市の名前によって並べ替えられ、州でグループ化された、データ コレクションのビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="7dcbe-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="7dcbe-110">その後、次の例のように、そのビューをバインディング ソースにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7dcbe-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="7dcbe-111"><xref:System.Windows.Data.XmlDataProvider> リソースで定義されている XML データへのバインディングでは、XML 名の前に @ 記号を付けます。</span><span class="sxs-lookup"><span data-stu-id="7dcbe-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="7dcbe-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7dcbe-112">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="7dcbe-113">データ コレクションの既定のビューを取得する</span><span class="sxs-lookup"><span data-stu-id="7dcbe-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="7dcbe-114">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="7dcbe-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7dcbe-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7dcbe-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
