---
title: '方法 : ListView のカスタム表示モードを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243220"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="2569e-102">方法: リスト ビューのカスタム ビュー モードを作成する</span><span class="sxs-lookup"><span data-stu-id="2569e-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="2569e-103">この例では、コントロールのカスタム<xref:System.Windows.Controls.ListView.View%2A>モードを作成<xref:System.Windows.Controls.ListView>する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2569e-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2569e-104">例</span><span class="sxs-lookup"><span data-stu-id="2569e-104">Example</span></span>  
 <span data-ttu-id="2569e-105">コントロールのカスタム<xref:System.Windows.Controls.ViewBase>ビューを作成するときには、このクラスを<xref:System.Windows.Controls.ListView>使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2569e-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="2569e-106">クラスから派生したビュー モードを`PlainView`次の例に<xref:System.Windows.Controls.ViewBase>示します。</span><span class="sxs-lookup"><span data-stu-id="2569e-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="2569e-107">カスタム ビューにスタイルを適用するには、 クラス<xref:System.Windows.Style>を使用します。</span><span class="sxs-lookup"><span data-stu-id="2569e-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="2569e-108">次の例では、<xref:System.Windows.Style>ビュー`PlainView`モードの を定義します。</span><span class="sxs-lookup"><span data-stu-id="2569e-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="2569e-109">前の例では、このスタイルは、 に定義されている<xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>プロパティの値として設定されています。 `PlainView`</span><span class="sxs-lookup"><span data-stu-id="2569e-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="2569e-110">カスタム ビュー モードでデータのレイアウトを定義するには、オブジェクト<xref:System.Windows.DataTemplate>を定義します。</span><span class="sxs-lookup"><span data-stu-id="2569e-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="2569e-111">ビュー モードでデータ<xref:System.Windows.DataTemplate>を表示するために使用できる を定義する`PlainView`例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2569e-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="2569e-112">次の例は、前の例<xref:System.Windows.ResourceKey>で定義`PlainView`された を使用する<xref:System.Windows.DataTemplate>ビュー モードの を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2569e-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="2569e-113"><xref:System.Windows.Controls.ListView>プロパティをリソース キーに設定すると、コントロールは<xref:System.Windows.Controls.ListView.View%2A>カスタム ビューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2569e-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="2569e-114">次の例は、`PlainView`<xref:System.Windows.Controls.ListView>のビュー モードとして指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2569e-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="2569e-115">完全なサンプルについては、「[複数のビューを含むリストビュー (C#)」](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp)または[「複数ビューを含むリストビュー (Visual Basic)」を参照](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)してください。</span><span class="sxs-lookup"><span data-stu-id="2569e-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2569e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2569e-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="2569e-117">操作方法に関するトピック</span><span class="sxs-lookup"><span data-stu-id="2569e-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="2569e-118">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="2569e-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="2569e-119">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="2569e-119">GridView Overview</span></span>](gridview-overview.md)
