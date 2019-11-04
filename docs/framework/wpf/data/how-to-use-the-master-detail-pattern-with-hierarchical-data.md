---
title: '方法 : 階層データでマスター詳細パターンを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 2e7d9ceed3ab8385f07d87ecdb92c0a99d410b40
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459083"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="6b186-102">方法 : 階層データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="6b186-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="6b186-103">この例では、マスター/詳細シナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b186-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b186-104">例</span><span class="sxs-lookup"><span data-stu-id="6b186-104">Example</span></span>  
 <span data-ttu-id="6b186-105">この例では、`LeagueList` は `Leagues`のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="6b186-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="6b186-106">各 `League` には `Divisions`の `Name` とコレクションがあり、各 `Division` には名前と `Teams`のコレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="6b186-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="6b186-107">各 `Team` にはチーム名があります。</span><span class="sxs-lookup"><span data-stu-id="6b186-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="6b186-108">次に示すのは、この例のスクリーンショットです。</span><span class="sxs-lookup"><span data-stu-id="6b186-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="6b186-109">`Divisions` <xref:System.Windows.Controls.ListBox> によって、`Leagues` <xref:System.Windows.Controls.ListBox> の選択が自動的に追跡され、対応するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b186-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="6b186-110">`Teams` <xref:System.Windows.Controls.ListBox> は、他の2つの <xref:System.Windows.Controls.ListBox> コントロールでの選択を追跡します。</span><span class="sxs-lookup"><span data-stu-id="6b186-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![マスター&#45;詳細シナリオの例を示すスクリーンショット。](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="6b186-112">この例では、次の2つの点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b186-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="6b186-113">3つの <xref:System.Windows.Controls.ListBox> コントロールは、同じソースにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="6b186-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="6b186-114">バインドの <xref:System.Windows.Data.Binding.Path%2A> プロパティを設定して、<xref:System.Windows.Controls.ListBox> に表示するデータのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b186-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="6b186-115"><xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> プロパティは、追跡する選択範囲の <xref:System.Windows.Controls.ListBox> コントロールで `true` するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b186-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="6b186-116">このプロパティを設定すると、選択した項目が常に <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>として設定されます。</span><span class="sxs-lookup"><span data-stu-id="6b186-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="6b186-117">また、<xref:System.Windows.Controls.ListBox> が <xref:System.Windows.Data.CollectionViewSource>からデータを取得する場合は、選択と通貨が自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="6b186-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="6b186-118">[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] データを使用している場合、この手法は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="6b186-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="6b186-119">例については、「[階層 XML データでマスター詳細パターンを使用する](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b186-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b186-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b186-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="6b186-121">コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="6b186-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="6b186-122">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="6b186-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="6b186-123">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="6b186-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="6b186-124">方法トピック</span><span class="sxs-lookup"><span data-stu-id="6b186-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
