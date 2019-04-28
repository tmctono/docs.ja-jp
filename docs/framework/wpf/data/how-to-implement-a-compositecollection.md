---
title: '方法: CompositeCollection を実装する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 8361c2bfa9c125aeadf0a62ca86af1855e5c3dbc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931678"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="c62a2-102">方法: CompositeCollection を実装する</span><span class="sxs-lookup"><span data-stu-id="c62a2-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="c62a2-103">例</span><span class="sxs-lookup"><span data-stu-id="c62a2-103">Example</span></span>  
 <span data-ttu-id="c62a2-104">次の例では、1 つのリストを使用して複数のコレクションと項目を表示する方法を示しています、<xref:System.Windows.Data.CompositeCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="c62a2-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="c62a2-105">この例で`GreekGods`は、<xref:System.Collections.ObjectModel.ObservableCollection%601>の`GreekGod`カスタム オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c62a2-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="c62a2-106">データ テンプレートが定義されているように`GreekGod`オブジェクトと`GreekHero`オブジェクトは、gold とシアンの前景の色をそれぞれ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c62a2-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c62a2-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="c62a2-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="c62a2-108">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="c62a2-108">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="c62a2-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="c62a2-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
