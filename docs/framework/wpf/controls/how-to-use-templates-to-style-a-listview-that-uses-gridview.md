---
title: '方法: テンプレートを使用して、GridView を使用する ListView のスタイルを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: 1caa652c4a2a3a7d0a8d40fe703df7a3e8038c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699124"
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="f13b1-102">方法: テンプレートを使用して、GridView を使用する ListView のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="f13b1-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="f13b1-103">この例からは、<xref:System.Windows.DataTemplate> オブジェクトと <xref:System.Windows.Style> オブジェクトを使用することで、<xref:System.Windows.Controls.GridView> 表示モードを使用する <xref:System.Windows.Controls.ListView> コントロールの外観を指定する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="f13b1-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f13b1-104">例</span><span class="sxs-lookup"><span data-stu-id="f13b1-104">Example</span></span>  
 <span data-ttu-id="f13b1-105">次の例では、<xref:System.Windows.Controls.GridViewColumn> の列ヘッダーの外観をカスタマイズする <xref:System.Windows.Style> オブジェクトと <xref:System.Windows.DataTemplate> オブジェクトを示します。</span><span class="sxs-lookup"><span data-stu-id="f13b1-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="f13b1-106">次の例では、これらの <xref:System.Windows.Style> オブジェクトと <xref:System.Windows.DataTemplate> オブジェクトを使用し、<xref:System.Windows.Controls.GridViewColumn> の <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> プロパティと <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> プロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f13b1-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="f13b1-107"><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> プロパティによって列セルの内容が定義されます。</span><span class="sxs-lookup"><span data-stu-id="f13b1-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="f13b1-108"><xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> と <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> は、<xref:System.Windows.Controls.GridView> コントロールの列ヘッダーの外観をカスタマイズできるいくつかのプロパティのうちの 2 つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="f13b1-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="f13b1-109">詳細については、[GridView の列ヘッダーのスタイルとテンプレートの概要](gridview-column-header-styles-and-templates-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f13b1-109">For more information, see [GridView Column Header Styles and Templates Overview](gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="f13b1-110">次の例では、<xref:System.Windows.Controls.GridViewColumn> 内のセルの外観をカスタマイズする <xref:System.Windows.DataTemplate> を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f13b1-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="f13b1-111">次の例では、この <xref:System.Windows.DataTemplate> を使用し、<xref:System.Windows.Controls.GridViewColumn> セルのコンテンツを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f13b1-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="f13b1-112">このテンプレートは、前の <xref:System.Windows.Controls.GridViewColumn> の例に含まれる <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> プロパティの代わりに使用されています。</span><span class="sxs-lookup"><span data-stu-id="f13b1-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="f13b1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f13b1-113">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="f13b1-114">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="f13b1-114">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="f13b1-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f13b1-115">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="f13b1-116">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="f13b1-116">ListView Overview</span></span>](listview-overview.md)
