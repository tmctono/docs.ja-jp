---
title: '方法: CompositeCollection を実装する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: b3450cdc476b7090251a06b5b2b2718d29e18209
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454024"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="7bc59-102">方法: CompositeCollection を実装する</span><span class="sxs-lookup"><span data-stu-id="7bc59-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="7bc59-103">例</span><span class="sxs-lookup"><span data-stu-id="7bc59-103">Example</span></span>  
 <span data-ttu-id="7bc59-104">次の例では、<xref:System.Windows.Data.CompositeCollection> クラスを使用して、複数のコレクションと項目を 1 つのリストとして表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7bc59-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="7bc59-105">この例では、`GreekGods` は `GreekGod` カスタム オブジェクトの <xref:System.Collections.ObjectModel.ObservableCollection%601> です。</span><span class="sxs-lookup"><span data-stu-id="7bc59-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="7bc59-106">データ テンプレートは、`GreekGod` オブジェクトと `GreekHero` オブジェクトがそれぞれゴールドとシアンの前景色で表示されるように定義されています。</span><span class="sxs-lookup"><span data-stu-id="7bc59-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7bc59-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bc59-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="7bc59-108">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="7bc59-108">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7bc59-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7bc59-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
