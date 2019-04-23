---
title: '方法: コレクションにバインドして選択に基づく情報を表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: bb7d4c89e63982a3052857dcb50d04d36d9517dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314394"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="0c81a-102">方法: コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="0c81a-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="0c81a-103">データ バインドがある場合、単純なマスター詳細シナリオで<xref:System.Windows.Controls.ItemsControl>など、<xref:System.Windows.Controls.ListBox>します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="0c81a-104">ユーザー選択に基づいて、選択した項目の詳細についてを表示します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="0c81a-105">この例では、このシナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c81a-106">例</span><span class="sxs-lookup"><span data-stu-id="0c81a-106">Example</span></span>  
 <span data-ttu-id="0c81a-107">この例で`People`は、<xref:System.Collections.ObjectModel.ObservableCollection%601>の`Person`クラス。</span><span class="sxs-lookup"><span data-stu-id="0c81a-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="0c81a-108">これは、`Person`クラスには、3 つのプロパティが含まれています: `FirstName`、 `LastName`、および`HomeTown`、すべての種類の`string`します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="0c81a-109"><xref:System.Windows.Controls.ContentControl> 、次を使用して<xref:System.Windows.DataTemplate>を定義する方法の情報を`Person`が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c81a-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="0c81a-110">この例の生成のスクリーン ショットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="0c81a-111"><xref:System.Windows.Controls.ContentControl>選択されているユーザーの他のプロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="0c81a-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="0c81a-112">![コレクションへのバインディング](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="0c81a-112">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="0c81a-113">この例では、2 つの処理は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0c81a-113">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="0c81a-114"><xref:System.Windows.Controls.ListBox>と<xref:System.Windows.Controls.ContentControl>を同じソースにバインドします。</span><span class="sxs-lookup"><span data-stu-id="0c81a-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="0c81a-115"><xref:System.Windows.Data.Binding.Path%2A>両方のコントロールは、コレクション オブジェクト全体にバインドするため、どちらのバインドのプロパティが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="0c81a-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="0c81a-116">設定する必要があります、<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>プロパティを`true`これが機能します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="0c81a-117">このプロパティ設定によって、選択した項目として常に設定されている、<xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="0c81a-118">また場合、<xref:System.Windows.Controls.ListBox>からデータを取得しますが、<xref:System.Windows.Data.CollectionViewSource>の選択と通貨を自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="0c81a-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="0c81a-119">なお、`Person`オーバーライド、`ToString`メソッドは次の方法です。</span><span class="sxs-lookup"><span data-stu-id="0c81a-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="0c81a-120">既定で、<xref:System.Windows.Controls.ListBox>呼び出し`ToString`バインドのコレクション内の各オブジェクトの文字列表現を表示します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="0c81a-121">その理由は各`Person`の最初の名前として表示されます、<xref:System.Windows.Controls.ListBox>します。</span><span class="sxs-lookup"><span data-stu-id="0c81a-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="0c81a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c81a-122">See also</span></span>

- [<span data-ttu-id="0c81a-123">階層データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="0c81a-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="0c81a-124">階層 XML データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="0c81a-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="0c81a-125">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="0c81a-125">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="0c81a-126">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="0c81a-126">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="0c81a-127">方法トピック</span><span class="sxs-lookup"><span data-stu-id="0c81a-127">How-to Topics</span></span>](data-binding-how-to-topics.md)
