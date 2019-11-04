---
title: '方法 : LINQ クエリの結果にバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d21ac5f366e001ea76d6eda64ed62583248796f6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454418"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="67afa-102">方法 : LINQ クエリの結果にバインドする</span><span class="sxs-lookup"><span data-stu-id="67afa-102">How to: Bind to the Results of a LINQ Query</span></span>

<span data-ttu-id="67afa-103">この例では、LINQ クエリを実行し、その結果にバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="67afa-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>

## <a name="example"></a><span data-ttu-id="67afa-104">例</span><span class="sxs-lookup"><span data-stu-id="67afa-104">Example</span></span>

<span data-ttu-id="67afa-105">次の例では、2つのリストボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="67afa-105">The following example creates two list boxes.</span></span> <span data-ttu-id="67afa-106">最初のリストボックスには、3つのリスト項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67afa-106">The first list box contains three list items.</span></span>

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

<span data-ttu-id="67afa-107">最初のリストボックスから項目を選択すると、次のイベントハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="67afa-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="67afa-108">この例では、`Tasks` は `Task` オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="67afa-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="67afa-109">`Task` クラスには、`Priority`という名前のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="67afa-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="67afa-110">このイベントハンドラーは、選択した優先順位値を持つ `Task` オブジェクトのコレクションを返す LINQ クエリを実行し、それを <xref:System.Windows.FrameworkElement.DataContext%2A>として設定します。</span><span class="sxs-lookup"><span data-stu-id="67afa-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

<span data-ttu-id="67afa-111"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 値が `{Binding}`に設定されているため、2番目のリストボックスはそのコレクションにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="67afa-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="67afa-112">その結果、返されたコレクションが (`myTaskTemplate` <xref:System.Windows.DataTemplate>に基づいて) 表示されます。</span><span class="sxs-lookup"><span data-stu-id="67afa-112">As a result, it displays the returned collection (based on the `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span></span>

## <a name="see-also"></a><span data-ttu-id="67afa-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="67afa-113">See also</span></span>

- [<span data-ttu-id="67afa-114">XAML でデータをバインディング可能にする</span><span class="sxs-lookup"><span data-stu-id="67afa-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="67afa-115">コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="67afa-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="67afa-116">WPF Version 4.5 の新機能</span><span class="sxs-lookup"><span data-stu-id="67afa-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="67afa-117">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="67afa-117">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
