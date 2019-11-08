---
title: '方法 : 階層 XML データでマスター詳細パターンを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733418"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="f3940-102">方法 : 階層 XML データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="f3940-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="f3940-103">この例では、XML データを使用してマスター詳細シナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3940-103">This example shows how to implement the master-detail scenario with XML data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3940-104">例</span><span class="sxs-lookup"><span data-stu-id="f3940-104">Example</span></span>  
 <span data-ttu-id="f3940-105">この例は、「[階層データでマスター詳細パターンを使用する](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)」で説明されている例の XML データバージョンです。</span><span class="sxs-lookup"><span data-stu-id="f3940-105">This example is the XML data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="f3940-106">この例では、データは `League.xml`ファイルからのものです。</span><span class="sxs-lookup"><span data-stu-id="f3940-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="f3940-107">3番目の <xref:System.Windows.Controls.ListBox> コントロールが、<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> プロパティにバインドすることによって、2番目の <xref:System.Windows.Controls.ListBox> の選択の変化を追跡する方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f3940-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="f3940-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3940-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="f3940-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f3940-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
