---
title: '方法 : CompositeCollection を実装する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: b3450cdc476b7090251a06b5b2b2718d29e18209
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454024"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="932c3-102">方法 : CompositeCollection を実装する</span><span class="sxs-lookup"><span data-stu-id="932c3-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="932c3-103">例</span><span class="sxs-lookup"><span data-stu-id="932c3-103">Example</span></span>  
 <span data-ttu-id="932c3-104">次の例では、<xref:System.Windows.Data.CompositeCollection> クラスを使用して、複数のコレクションと項目を1つのリストとして表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="932c3-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="932c3-105">この例では、`GreekGods` は `GreekGod` カスタムオブジェクトの <xref:System.Collections.ObjectModel.ObservableCollection%601> です。</span><span class="sxs-lookup"><span data-stu-id="932c3-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="932c3-106">データテンプレートは、`GreekGod` オブジェクトと `GreekHero` オブジェクトがそれぞれ金色とシアンの前景色で表示されるように定義されています。</span><span class="sxs-lookup"><span data-stu-id="932c3-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="932c3-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="932c3-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="932c3-108">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="932c3-108">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="932c3-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="932c3-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
