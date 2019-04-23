---
title: '方法: CompositeCollection を実装する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 8361c2bfa9c125aeadf0a62ca86af1855e5c3dbc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091165"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="42650-102">方法: CompositeCollection を実装する</span><span class="sxs-lookup"><span data-stu-id="42650-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="42650-103">例</span><span class="sxs-lookup"><span data-stu-id="42650-103">Example</span></span>  
 <span data-ttu-id="42650-104">次の例では、1 つのリストを使用して複数のコレクションと項目を表示する方法を示しています、<xref:System.Windows.Data.CompositeCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="42650-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="42650-105">この例で`GreekGods`は、<xref:System.Collections.ObjectModel.ObservableCollection%601>の`GreekGod`カスタム オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="42650-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="42650-106">データ テンプレートが定義されているように`GreekGod`オブジェクトと`GreekHero`オブジェクトは、gold とシアンの前景の色をそれぞれ表示されます。</span><span class="sxs-lookup"><span data-stu-id="42650-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="42650-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="42650-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="42650-108">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="42650-108">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="42650-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="42650-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
