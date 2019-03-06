---
title: '方法: データ CollectionView のオブジェクト間を移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 9272a2f635a62abdac2746f2c8cce515812706f6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355780"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="c6faa-102">方法: データ CollectionView のオブジェクト間を移動する</span><span class="sxs-lookup"><span data-stu-id="c6faa-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="c6faa-103">ビューでは、並べ替え、フィルター処理、またはグループ化に応じて、さまざまな方法で表示する同じデータ収集を許可します。</span><span class="sxs-lookup"><span data-stu-id="c6faa-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="c6faa-104">ビューは、現在のレコード ポインターの概念を提供し、ポインターの移動を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c6faa-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="c6faa-105">この例で提供される機能を使用してデータ コレクションのオブジェクト間を移動するほか、現在のオブジェクトを取得する方法を示しています、<xref:System.Windows.Data.CollectionView>クラス。</span><span class="sxs-lookup"><span data-stu-id="c6faa-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6faa-106">例</span><span class="sxs-lookup"><span data-stu-id="c6faa-106">Example</span></span>  
 <span data-ttu-id="c6faa-107">この例で`myCollectionView`は、<xref:System.Windows.Data.CollectionView>ビューでバインドされたコレクションであるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c6faa-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="c6faa-108">次の例では、`OnButton`のイベント ハンドラー、`Previous`と`Next`により、ユーザー データのコレクションを移動するボタンであるアプリケーションでは、ボタン。</span><span class="sxs-lookup"><span data-stu-id="c6faa-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="c6faa-109">なお、<xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A>と<xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A>プロパティを報告するかどうか、現在のレコード ポインターに来た、先頭と末尾のリストのそれぞれためを<xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A>と<xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>として適切に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c6faa-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="c6faa-110"><xref:System.Windows.Data.CollectionView.CurrentItem%2A>としてキャストは、ビューのプロパティ、`Order`コレクション内の現在の注文アイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="c6faa-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="c6faa-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6faa-111">See also</span></span>
- [<span data-ttu-id="c6faa-112">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="c6faa-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="c6faa-113">ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="c6faa-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="c6faa-114">ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c6faa-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="c6faa-115">XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="c6faa-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="c6faa-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="c6faa-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
