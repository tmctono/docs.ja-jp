---
title: '方法: ListView の列の水平方向の配置を変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 528a711c1cf7992bb32c0aa4d6e81d71744c9f80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911067"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="478be-102">方法: ListView の列の水平方向の配置を変更する</span><span class="sxs-lookup"><span data-stu-id="478be-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="478be-103">既定で各列のコンテンツを<xref:System.Windows.Controls.ListViewItem>は左揃えにします。</span><span class="sxs-lookup"><span data-stu-id="478be-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="478be-104">提供することで各列の配置を変更することができます、<xref:System.Windows.DataTemplate>と設定、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティ内の要素を<xref:System.Windows.DataTemplate>します。</span><span class="sxs-lookup"><span data-stu-id="478be-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="478be-105">このトピックでは、方法、<xref:System.Windows.Controls.ListView>既定で 1 つの列の配置を変更する方法とそのコンテンツを配置、<xref:System.Windows.Controls.ListView>します。</span><span class="sxs-lookup"><span data-stu-id="478be-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="478be-106">例</span><span class="sxs-lookup"><span data-stu-id="478be-106">Example</span></span>  
 <span data-ttu-id="478be-107">次の例では、データ、`Title`と`ISBN`列を左揃え。</span><span class="sxs-lookup"><span data-stu-id="478be-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="478be-108">配置を変更する、`ISBN`列、ことを指定する必要があります、<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>の各プロパティ<xref:System.Windows.Controls.ListViewItem>は<xref:System.Windows.HorizontalAlignment.Stretch>いるため、各要素<xref:System.Windows.Controls.ListViewItem>にまたがるまたは各列の幅全体に合わせて配置します。</span><span class="sxs-lookup"><span data-stu-id="478be-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="478be-109"><xref:System.Windows.Controls.ListView>がバインドされているデータ ソースには、スタイル設定を作成する必要があります、<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>します。</span><span class="sxs-lookup"><span data-stu-id="478be-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="478be-110">次に、使用する必要があります、<xref:System.Windows.DataTemplate>を使用する代わりにコンテンツを表示する、<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="478be-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="478be-111">表示する、`ISBN`テンプレートごとの<xref:System.Windows.DataTemplate>だけ含めることができます、<xref:System.Windows.Controls.TextBlock>を持つその<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティに設定<xref:System.Windows.HorizontalAlignment.Right>します。</span><span class="sxs-lookup"><span data-stu-id="478be-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="478be-112">次の例は、スタイルを定義および<xref:System.Windows.DataTemplate>ために必要な`ISBN`右揃えの列と変更、<xref:System.Windows.Controls.GridViewColumn>参照に、 <xref:System.Windows.DataTemplate>。</span><span class="sxs-lookup"><span data-stu-id="478be-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="478be-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="478be-113">See also</span></span>

- [<span data-ttu-id="478be-114">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="478be-114">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="478be-115">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="478be-115">Data Templating Overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="478be-116">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="478be-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="478be-117">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="478be-117">ListView Overview</span></span>](listview-overview.md)
