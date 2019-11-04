---
title: '方法 : コレクションにバインドして選択に基づく情報を表示する'
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
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459150"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="36d50-102">方法 : コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="36d50-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="36d50-103">単純なマスター/詳細シナリオでは、<xref:System.Windows.Controls.ListBox>などのデータバインド <xref:System.Windows.Controls.ItemsControl> があります。</span><span class="sxs-lookup"><span data-stu-id="36d50-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="36d50-104">ユーザーの選択に基づいて、選択した項目に関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="36d50-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="36d50-105">この例は、このシナリオを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="36d50-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36d50-106">例</span><span class="sxs-lookup"><span data-stu-id="36d50-106">Example</span></span>  
 <span data-ttu-id="36d50-107">この例では、`People` は `Person` クラスの <xref:System.Collections.ObjectModel.ObservableCollection%601> です。</span><span class="sxs-lookup"><span data-stu-id="36d50-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="36d50-108">この `Person` クラスには、`FirstName`、`LastName`、および `HomeTown`の3つのプロパティが含まれています。すべての型 `string`です。</span><span class="sxs-lookup"><span data-stu-id="36d50-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="36d50-109"><xref:System.Windows.Controls.ContentControl> は、`Person` の情報の表示方法を定義する次の <xref:System.Windows.DataTemplate> を使用します。</span><span class="sxs-lookup"><span data-stu-id="36d50-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="36d50-110">次に、この例で生成される内容のスクリーンショットを示します。</span><span class="sxs-lookup"><span data-stu-id="36d50-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="36d50-111"><xref:System.Windows.Controls.ContentControl> には、選択したユーザーの他のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36d50-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="36d50-112">![コレクションへのバインド](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="36d50-112">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="36d50-113">この例では、次の2つの点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="36d50-113">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="36d50-114"><xref:System.Windows.Controls.ListBox> と <xref:System.Windows.Controls.ContentControl> は同じソースにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="36d50-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="36d50-115">両方のコントロールがコレクションオブジェクト全体にバインドされるため、両方のバインドの <xref:System.Windows.Data.Binding.Path%2A> プロパティは指定されません。</span><span class="sxs-lookup"><span data-stu-id="36d50-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="36d50-116">これを機能させるには、<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> プロパティを `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36d50-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="36d50-117">このプロパティを設定すると、選択した項目が常に <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>として設定されます。</span><span class="sxs-lookup"><span data-stu-id="36d50-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="36d50-118">また、<xref:System.Windows.Controls.ListBox> が <xref:System.Windows.Data.CollectionViewSource>からデータを取得する場合は、選択と通貨が自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="36d50-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="36d50-119">`Person` クラスは、次のように `ToString` メソッドをオーバーライドすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="36d50-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="36d50-120">既定では、<xref:System.Windows.Controls.ListBox> は `ToString` を呼び出し、バインドされたコレクション内の各オブジェクトの文字列形式を表示します。</span><span class="sxs-lookup"><span data-stu-id="36d50-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="36d50-121">そのため、各 `Person` が <xref:System.Windows.Controls.ListBox>の名として表示されます。</span><span class="sxs-lookup"><span data-stu-id="36d50-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="36d50-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="36d50-122">See also</span></span>

- [<span data-ttu-id="36d50-123">階層データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="36d50-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="36d50-124">階層 XML データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="36d50-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="36d50-125">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="36d50-125">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="36d50-126">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="36d50-126">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="36d50-127">方法トピック</span><span class="sxs-lookup"><span data-stu-id="36d50-127">How-to Topics</span></span>](data-binding-how-to-topics.md)
