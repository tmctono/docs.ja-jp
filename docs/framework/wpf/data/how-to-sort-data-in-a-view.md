---
title: '方法: ビュー内のデータの並べ替え'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 32f73d3c3ba213778654f0d1ee7bbae16b9d845b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020726"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="08d41-102">方法: ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="08d41-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="08d41-103">この例では、ビュー内のデータを並べ替える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08d41-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08d41-104">例</span><span class="sxs-lookup"><span data-stu-id="08d41-104">Example</span></span>  
 <span data-ttu-id="08d41-105">次の例では、単純な<xref:System.Windows.Controls.ListBox>と<xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="08d41-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="08d41-106"><xref:System.Windows.Controls.Primitives.ButtonBase.Click>ボタンのイベント ハンドラーには内の項目の並べ替えにロジックが含まれています、<xref:System.Windows.Controls.ListBox>降順にします。</span><span class="sxs-lookup"><span data-stu-id="08d41-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="08d41-107">これを行うために項目を追加、<xref:System.Windows.Controls.ListBox>この方法を追加すること、<xref:System.Windows.Controls.ItemCollection>の<xref:System.Windows.Controls.ListBox>、および<xref:System.Windows.Controls.ItemCollection>から派生した、<xref:System.Windows.Data.CollectionView>クラス。</span><span class="sxs-lookup"><span data-stu-id="08d41-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="08d41-108">バインドしている場合、<xref:System.Windows.Controls.ListBox>を使用してコレクションに、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>プロパティの並べ替えには同じ手法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="08d41-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="08d41-109">ビューのオブジェクトへの参照がある限り、他のコレクション ビューのコンテンツを並べ替えるには同じ手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="08d41-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="08d41-110">ビューを取得する方法の例は、次を参照してください。[データ コレクションの既定のビューを取得](how-to-get-the-default-view-of-a-data-collection.md)します。</span><span class="sxs-lookup"><span data-stu-id="08d41-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="08d41-111">別の例では、次を参照してください。[を GridView の列のヘッダーがクリックされたときの並べ替え](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)します。</span><span class="sxs-lookup"><span data-stu-id="08d41-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="08d41-112">ビューの詳細については、コレクションへのバインドを参照してください。[データ バインディングの概要](data-binding-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="08d41-112">For more information about views, see Binding to Collections in [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="08d41-113">並べ替えのロジックを適用する方法の例については[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]を参照してください[並べ替えとグループを使用して XAML でビューをデータ](how-to-sort-and-group-data-using-a-view-in-xaml.md)します。</span><span class="sxs-lookup"><span data-stu-id="08d41-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d41-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="08d41-114">See also</span></span>

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="08d41-115">ヘッダーがクリックされたときに GridView 列を並べ替える</span><span class="sxs-lookup"><span data-stu-id="08d41-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="08d41-116">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="08d41-116">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="08d41-117">ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="08d41-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="08d41-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="08d41-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
