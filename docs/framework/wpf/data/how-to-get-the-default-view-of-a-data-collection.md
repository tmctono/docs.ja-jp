---
title: '方法 : データ コレクションの既定のビューを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459116"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="b3922-102">方法 : データ コレクションの既定のビューを取得する</span><span class="sxs-lookup"><span data-stu-id="b3922-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="b3922-103">ビューでは、並べ替え、フィルター処理、グループ化の基準に応じて、同じデータコレクションをさまざまな方法で表示できます。</span><span class="sxs-lookup"><span data-stu-id="b3922-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="b3922-104">すべてのコレクションには共有された既定のビューが1つあります。これは、バインディングがソースとしてコレクションを指定するときに実際のバインディングソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3922-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="b3922-105">この例は、コレクションの既定のビューを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3922-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3922-106">例</span><span class="sxs-lookup"><span data-stu-id="b3922-106">Example</span></span>  
 <span data-ttu-id="b3922-107">ビューを作成するには、コレクションへのオブジェクト参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3922-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="b3922-108">このデータオブジェクトを取得するには、データコンテキストを取得するか、データソースのプロパティを取得するか、またはバインディングのプロパティを取得して、独自の分離コードオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="b3922-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="b3922-109">この例では、データオブジェクトの <xref:System.Windows.FrameworkElement.DataContext%2A> を取得し、それを使用してこのコレクションの既定のコレクションビューを直接取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b3922-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="b3922-110">この例では、ルート要素は <xref:System.Windows.Controls.StackPanel>です。</span><span class="sxs-lookup"><span data-stu-id="b3922-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="b3922-111"><xref:System.Windows.FrameworkElement.DataContext%2A> が*Mydatasource*に設定されています。これは、 *Order*オブジェクトの <xref:System.Collections.ObjectModel.ObservableCollection%601> であるデータプロバイダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="b3922-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="b3922-112">または、<xref:System.Windows.Data.CollectionViewSource> クラスを使用して、独自のコレクションビューをインスタンス化し、バインドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b3922-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="b3922-113">このコレクションビューは、直接バインドするコントロールによってのみ共有されます。</span><span class="sxs-lookup"><span data-stu-id="b3922-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="b3922-114">例については、「[データバインディングの概要](../../../desktop-wpf/data/data-binding-overview.md)」の「ビューを作成する方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3922-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="b3922-115">コレクションビューで提供される機能の例については、「[ビュー内のデータの並べ替え](how-to-sort-data-in-a-view.md)」、「[ビューのデータのフィルター処理](how-to-filter-data-in-a-view.md)」、および「[データ CollectionView 内のオブジェクト間の移動](how-to-navigate-through-the-objects-in-a-data-collectionview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3922-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3922-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3922-116">See also</span></span>

- [<span data-ttu-id="b3922-117">XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="b3922-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="b3922-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="b3922-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
