---
title: '方法: Windows フォームでデータ間を移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 452aacab4580a3b07168daa6b7c03740dc98620b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583732"
---
# <a name="how-to-navigate-data-in-windows-forms"></a><span data-ttu-id="627b4-102">方法: Windows フォームでデータ間を移動する</span><span class="sxs-lookup"><span data-stu-id="627b4-102">How to: Navigate Data in Windows Forms</span></span>
<span data-ttu-id="627b4-103">Windows アプリケーションでは、データ ソース内のレコードをナビゲートする最も簡単な方法は、バインドする、<xref:System.Windows.Forms.BindingSource>コンポーネントをデータ ソースとし、バインド コントロールを<xref:System.Windows.Forms.BindingSource>します。</span><span class="sxs-lookup"><span data-stu-id="627b4-103">In a Windows application, the easiest way to navigate through records in a data source is to bind a <xref:System.Windows.Forms.BindingSource> component to the data source and then bind controls to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="627b4-104">組み込みのナビゲーション メソッドを使用することができますし、<xref:System.Windows.Forms.BindingSource>このような<xref:System.Windows.Forms.BindingSource.MoveNext%2A>、 <xref:System.Windows.Forms.BindingSource.MoveLast%2A>、<xref:System.Windows.Forms.BindingSource.MovePrevious%2A>と<xref:System.Windows.Forms.BindingSource.MoveFirst%2A>します。</span><span class="sxs-lookup"><span data-stu-id="627b4-104">You can then use the built-in navigation method on the <xref:System.Windows.Forms.BindingSource> such a <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> and <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span></span> <span data-ttu-id="627b4-105">これらのメソッドを使用して、調整は、<xref:System.Windows.Forms.BindingSource.Position%2A>と<xref:System.Windows.Forms.BindingSource.Current%2A>のプロパティ、<xref:System.Windows.Forms.BindingSource>適切にします。</span><span class="sxs-lookup"><span data-stu-id="627b4-105">Using these methods will adjust the <xref:System.Windows.Forms.BindingSource.Position%2A> and <xref:System.Windows.Forms.BindingSource.Current%2A> properties of the <xref:System.Windows.Forms.BindingSource> appropriately.</span></span> <span data-ttu-id="627b4-106">項目を検索し、設定して、現在の項目として設定できる、<xref:System.Windows.Forms.BindingSource.Position%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="627b4-106">You can also find an item and set it as the current item by setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property.</span></span>  
  
### <a name="to-increment-the-position-in-a-data-source"></a><span data-ttu-id="627b4-107">データ ソース内の位置をインクリメントするには</span><span class="sxs-lookup"><span data-stu-id="627b4-107">To increment the position in a data source</span></span>  
  
1. <span data-ttu-id="627b4-108">設定、<xref:System.Windows.Forms.BindingSource.Position%2A>のプロパティ、<xref:System.Windows.Forms.BindingSource>に進むにはレコードの位置に、バインドされたデータ。</span><span class="sxs-lookup"><span data-stu-id="627b4-108">Set the <xref:System.Windows.Forms.BindingSource.Position%2A> property of the <xref:System.Windows.Forms.BindingSource> for your bound data to the record position to go to.</span></span> <span data-ttu-id="627b4-109">次の例を使用して、<xref:System.Windows.Forms.BindingSource.MoveNext%2A>のメソッド、<xref:System.Windows.Forms.BindingSource>インクリメント、<xref:System.Windows.Forms.BindingSource.Position%2A>プロパティと、`nextButton`がクリックされました。</span><span class="sxs-lookup"><span data-stu-id="627b4-109">The following example illustrates using the <xref:System.Windows.Forms.BindingSource.MoveNext%2A> method of the <xref:System.Windows.Forms.BindingSource> to increment the <xref:System.Windows.Forms.BindingSource.Position%2A> property when the `nextButton` is clicked.</span></span> <span data-ttu-id="627b4-110"><xref:System.Windows.Forms.BindingSource>に関連付けられている、`Customers`データセットのテーブル`Northwind`します。</span><span class="sxs-lookup"><span data-stu-id="627b4-110">The <xref:System.Windows.Forms.BindingSource> is associated with the `Customers` table of a dataset `Northwind`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="627b4-111">設定、<xref:System.Windows.Forms.BindingSource.Position%2A>最初または最後のレコードを超える値にプロパティにならない、エラー、.NET Framework での位置を一覧の境界外の値に設定することを許可しないされています。</span><span class="sxs-lookup"><span data-stu-id="627b4-111">Setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property to a value beyond the first or last record does not result in an error, as the .NET Framework will not allow you to set the position to a value outside the bounds of the list.</span></span> <span data-ttu-id="627b4-112">最初と最後のレコードを経過したかどうかを知るためにアプリケーションで重要な場合は、データ要素の数を超えますかどうかをテストするロジックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="627b4-112">If it is important in your application to know whether you have gone past the first or last record, include logic to test whether you will exceed the data element count.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a><span data-ttu-id="627b4-113">末尾または先頭が渡されるかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="627b4-113">To check whether you have passed the end or beginning</span></span>  
  
1. <span data-ttu-id="627b4-114"><xref:System.Windows.Forms.BindingSource.PositionChanged> イベントのイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="627b4-114">Create an event handler for the <xref:System.Windows.Forms.BindingSource.PositionChanged> event.</span></span> <span data-ttu-id="627b4-115">ハンドラーでは、提案された位置の値が実際のデータ要素の数を超えたかどうかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="627b4-115">In the handler, you can test whether the proposed position value has exceeded the actual data element count.</span></span>  
  
     <span data-ttu-id="627b4-116">次の例では、データの最後の要素に到達したかどうかをテストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="627b4-116">The following example illustrates how you can test whether you have reached the last data element.</span></span> <span data-ttu-id="627b4-117">最後の要素でない場合は、例では、**次**フォーム上のボタンが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="627b4-117">In the example, if you are at the last element, the **Next** button on the form is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="627b4-118">、コード内を移動する一覧を変更する必要があります再度有効にすることに注意してください、**次**ボタンをユーザーが新しいリストの全体の長さを表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="627b4-118">Be aware that, should you change the list you are navigating in code, you should re-enable the **Next** button, so that users may browse the entire length of the new list.</span></span> <span data-ttu-id="627b4-119">さらに、注意を上記<xref:System.Windows.Forms.BindingSource.PositionChanged>、特定のイベント<xref:System.Windows.Forms.BindingSource>に関連付けられて、イベント処理メソッドである必要がありますを使用します。</span><span class="sxs-lookup"><span data-stu-id="627b4-119">Additionally, be aware that the above <xref:System.Windows.Forms.BindingSource.PositionChanged> event for the specific <xref:System.Windows.Forms.BindingSource> you are working with needs to be associated with its event-handling method.</span></span> <span data-ttu-id="627b4-120">処理のためのメソッドの例を次に、<xref:System.Windows.Forms.BindingSource.PositionChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="627b4-120">The following is an example of a method for handling the <xref:System.Windows.Forms.BindingSource.PositionChanged> event:</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a><span data-ttu-id="627b4-121">項目を検索し、現在の項目として設定するには</span><span class="sxs-lookup"><span data-stu-id="627b4-121">To find an item and set it as the current item</span></span>  
  
1. <span data-ttu-id="627b4-122">現在の項目として設定するレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="627b4-122">Find the record you wish to set as the current item.</span></span> <span data-ttu-id="627b4-123">これを行うを使用して、<xref:System.Windows.Forms.BindingSource.Find%2A>のメソッド、<xref:System.Windows.Forms.BindingSource>場合は、データ ソースの実装、<xref:System.ComponentModel.IBindingList>します。</span><span class="sxs-lookup"><span data-stu-id="627b4-123">You can do this using the <xref:System.Windows.Forms.BindingSource.Find%2A> method of the <xref:System.Windows.Forms.BindingSource>, if your data source implements <xref:System.ComponentModel.IBindingList>.</span></span> <span data-ttu-id="627b4-124">データの例をいくつかは実装するソース<xref:System.ComponentModel.IBindingList>は<xref:System.ComponentModel.BindingList%601>と<xref:System.Data.DataView>します。</span><span class="sxs-lookup"><span data-stu-id="627b4-124">Some examples of data sources that implement <xref:System.ComponentModel.IBindingList> are <xref:System.ComponentModel.BindingList%601> and <xref:System.Data.DataView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="627b4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="627b4-125">See also</span></span>

- [<span data-ttu-id="627b4-126">Windows フォームがサポートするデータ ソース</span><span class="sxs-lookup"><span data-stu-id="627b4-126">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)
- [<span data-ttu-id="627b4-127">Windows フォーム データ バインドの変更通知</span><span class="sxs-lookup"><span data-stu-id="627b4-127">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="627b4-128">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="627b4-128">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
- [<span data-ttu-id="627b4-129">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="627b4-129">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
