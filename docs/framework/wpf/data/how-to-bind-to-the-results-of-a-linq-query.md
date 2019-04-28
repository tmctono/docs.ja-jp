---
title: '方法: LINQ クエリの結果にバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 5464ee9c59a7c99a83774a7535b9b3c422c1d2e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644418"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="72868-102">方法: LINQ クエリの結果にバインドする</span><span class="sxs-lookup"><span data-stu-id="72868-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="72868-103">この例では、LINQ クエリを実行し、結果にバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="72868-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72868-104">例</span><span class="sxs-lookup"><span data-stu-id="72868-104">Example</span></span>  
 <span data-ttu-id="72868-105">次の例では、2 つのリスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="72868-105">The following example creates two list boxes.</span></span> <span data-ttu-id="72868-106">最初のリスト ボックスには、次の 3 つのリスト項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="72868-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="72868-107">次のイベント ハンドラーを呼び出す最初のリスト ボックスから項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="72868-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="72868-108">この例で`Tasks`のコレクションである`Task`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72868-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="72868-109">`Task`クラスという名前のプロパティには`Priority`します。</span><span class="sxs-lookup"><span data-stu-id="72868-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="72868-110">このイベント ハンドラーのコレクションを返す LINQ クエリを実行する`Task`オブジェクトを選択した優先順位の値を持ちとして設定し、 <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="72868-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="72868-111">2 番目のリスト ボックスがそのコレクションにバインドするため、その<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>値に設定されて`{Binding}`します。</span><span class="sxs-lookup"><span data-stu-id="72868-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="72868-112">その結果、返されるコレクションが表示されます (に基づいて、 `myTaskTemplate` <xref:System.Windows.DataTemplate>)。</span><span class="sxs-lookup"><span data-stu-id="72868-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72868-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="72868-113">See also</span></span>

- [<span data-ttu-id="72868-114">XAML でデータをバインディング可能にする</span><span class="sxs-lookup"><span data-stu-id="72868-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="72868-115">コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="72868-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="72868-116">WPF Version 4.5 の新機能</span><span class="sxs-lookup"><span data-stu-id="72868-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="72868-117">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="72868-117">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="72868-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="72868-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
