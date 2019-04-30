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
ms.openlocfilehash: ca4439b574264ebebfda745f0765f750099bc95f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020739"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="7f9c8-102">方法: XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="7f9c8-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="7f9c8-103">この例でのデータ コレクションのビューを作成する方法を示しています。[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7f9c8-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="7f9c8-104">グループ化、並べ替え、フィルター処理、の機能と現在の項目の概念ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f9c8-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f9c8-105">例</span><span class="sxs-lookup"><span data-stu-id="7f9c8-105">Example</span></span>  
 <span data-ttu-id="7f9c8-106">は、次の例では、静的リソースの名前*配置*のコレクションとして定義されて*場所*オブジェクトは、各*場所*オブジェクトは、市区町村名で構成されていましたし、状態。</span><span class="sxs-lookup"><span data-stu-id="7f9c8-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="7f9c8-107">プレフィックス*src*名前空間にマップされているデータ ソース*場所*が定義されています。</span><span class="sxs-lookup"><span data-stu-id="7f9c8-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="7f9c8-108">プレフィックス*scm*にマップ`"clr-namespace:System.ComponentModel;assembly=WindowsBase"`と*dat*マップ`"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`します。</span><span class="sxs-lookup"><span data-stu-id="7f9c8-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="7f9c8-109">次の例では、市区町村名によって並べ替えられ、状態別にグループ化するデータ コレクションのビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f9c8-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="7f9c8-110">ビューは、次の例のように、バインディング ソースに指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f9c8-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="7f9c8-111">定義されている XML データへのバインドの<xref:System.Windows.Data.XmlDataProvider>リソース、XML 名の前に、@ 記号。</span><span class="sxs-lookup"><span data-stu-id="7f9c8-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="7f9c8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f9c8-112">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="7f9c8-113">データ コレクションの既定のビューを取得する</span><span class="sxs-lookup"><span data-stu-id="7f9c8-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="7f9c8-114">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="7f9c8-114">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="7f9c8-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7f9c8-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
