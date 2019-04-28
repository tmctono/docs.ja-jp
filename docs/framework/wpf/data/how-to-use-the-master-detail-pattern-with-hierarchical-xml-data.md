---
title: '方法: 階層 XML データでマスター詳細パターンを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: ba6c932f519ffa5c3c70ecb21eb9b5d08c40fb28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931756"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="3a8ff-102">方法: 階層 XML データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="3a8ff-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="3a8ff-103">この例でマスター詳細シナリオを実装する方法を示しています。[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]データ。</span><span class="sxs-lookup"><span data-stu-id="3a8ff-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a8ff-104">例</span><span class="sxs-lookup"><span data-stu-id="3a8ff-104">Example</span></span>  
 <span data-ttu-id="3a8ff-105">この例は、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]で説明した例のデータのバージョン[階層データでマスター詳細パターンを使用して](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a8ff-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="3a8ff-106">この例では、データ ファイルからは`League.xml`します。</span><span class="sxs-lookup"><span data-stu-id="3a8ff-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="3a8ff-107">注方法、3 番目の<xref:System.Windows.Controls.ListBox>コントロールは、2 番目の選択範囲の変更を追跡<xref:System.Windows.Controls.ListBox>にバインドしてその<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3a8ff-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="3a8ff-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a8ff-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="3a8ff-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="3a8ff-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
