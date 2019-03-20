---
title: '方法: GridView を使用して ListView コンテンツを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 1066869c80bf5bd87d656bcb4994c188ee0e8efc
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185611"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="9a24f-102">方法: GridView を使用して ListView コンテンツを表示する</span><span class="sxs-lookup"><span data-stu-id="9a24f-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="9a24f-103">この例は、定義する方法を示します、<xref:System.Windows.Controls.GridView>の表示モード、<xref:System.Windows.Controls.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="9a24f-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a24f-104">例</span><span class="sxs-lookup"><span data-stu-id="9a24f-104">Example</span></span>  
 <span data-ttu-id="9a24f-105">表示モードを定義することができます、<xref:System.Windows.Controls.GridView>を指定して<xref:System.Windows.Controls.GridViewColumn>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9a24f-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="9a24f-106">次の例は、定義する方法を示します<xref:System.Windows.Controls.GridViewColumn>に対して指定されているデータの内容にバインドするオブジェクト、<xref:System.Windows.Controls.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="9a24f-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="9a24f-107">これは、<xref:System.Windows.Controls.GridView>の例では、3 つを指定します<xref:System.Windows.Controls.GridViewColumn>にマップされているオブジェクト、 `FirstName`、 `LastName`、および`EmployeeNumber`のフィールド、`EmployeeInfoDataSource`として設定されている、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>の<xref:System.Windows.Controls.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="9a24f-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="9a24f-108">次の図は、この例の表示方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9a24f-108">The following illustration shows how this example appears.</span></span>  
  
 ![GridView 出力を含むの ListView を示すスクリーン ショット。](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a><span data-ttu-id="9a24f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a24f-110">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="9a24f-111">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="9a24f-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="9a24f-112">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="9a24f-112">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="9a24f-113">方法トピック</span><span class="sxs-lookup"><span data-stu-id="9a24f-113">How-to Topics</span></span>](listview-how-to-topics.md)
