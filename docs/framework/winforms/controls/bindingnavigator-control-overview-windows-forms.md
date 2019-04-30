---
title: BindingNavigator コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
ms.openlocfilehash: ad63f622aae55cb4175eddc93ab5e086965a8fe8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011789"
---
# <a name="bindingnavigator-control-overview-windows-forms"></a><span data-ttu-id="01cd8-102">BindingNavigator コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="01cd8-102">BindingNavigator Control Overview (Windows Forms)</span></span>
<span data-ttu-id="01cd8-103"><xref:System.Windows.Forms.BindingNavigator> コントロールを使用して、ユーザーが Windows フォームでデータを検索して変更するための標準化された手段を作成できます。</span><span class="sxs-lookup"><span data-stu-id="01cd8-103">You can use the <xref:System.Windows.Forms.BindingNavigator> control to create a standardized means for users to search and change data on a Windows Form.</span></span> <span data-ttu-id="01cd8-104"><xref:System.Windows.Forms.BindingNavigator> を <xref:System.Windows.Forms.BindingSource> コンポーネントと共に頻繁に使用して、ユーザーがフォームのデータ レコードを移動して、レコードと対話できるようにします。</span><span class="sxs-lookup"><span data-stu-id="01cd8-104">You frequently use <xref:System.Windows.Forms.BindingNavigator> with the <xref:System.Windows.Forms.BindingSource> component to enable users to move through data records on a form and interact with the records.</span></span>  
  
## <a name="how-the-bindingnavigator-works"></a><span data-ttu-id="01cd8-105">BindingNavigator のしくみ</span><span class="sxs-lookup"><span data-stu-id="01cd8-105">How the BindingNavigator Works</span></span>  

 <span data-ttu-id="01cd8-106">データの追加、データの削除、およびデータの移動という一般的なデータ関連の操作のほとんどで、<xref:System.Windows.Forms.BindingNavigator> コントロールは一連の <xref:System.Windows.Forms.ToolStripItem> オブジェクトを持つ <xref:System.Windows.Forms.ToolStrip> で構成されます。</span><span class="sxs-lookup"><span data-stu-id="01cd8-106">The <xref:System.Windows.Forms.BindingNavigator> control is composed of a <xref:System.Windows.Forms.ToolStrip> with a series of <xref:System.Windows.Forms.ToolStripItem> objects for most of the common data-related actions: adding data, deleting data, and navigating through data.</span></span> <span data-ttu-id="01cd8-107">既定では、<xref:System.Windows.Forms.BindingNavigator> コントロールにこれらの標準のボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="01cd8-107">By default, the <xref:System.Windows.Forms.BindingNavigator> control contains these standard buttons.</span></span> <span data-ttu-id="01cd8-108">次のスクリーン ショット、<xref:System.Windows.Forms.BindingNavigator>フォーム上のコントロール。</span><span class="sxs-lookup"><span data-stu-id="01cd8-108">The following screenshot shows the <xref:System.Windows.Forms.BindingNavigator> control on a form:</span></span>
  
 ![BindingNavigator コントロールを示すスクリーン ショット。](./media/bindingnavigator-control-overview-windows-forms/bindingnavigator-control-form.gif)  
  
 <span data-ttu-id="01cd8-110">コントロールの一覧と機能の説明を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-110">The following table lists the controls and describes their functions.</span></span>  
  
|<span data-ttu-id="01cd8-111">コントロール</span><span class="sxs-lookup"><span data-stu-id="01cd8-111">Control</span></span>|<span data-ttu-id="01cd8-112">関数</span><span class="sxs-lookup"><span data-stu-id="01cd8-112">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="01cd8-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> ボタン</span><span class="sxs-lookup"><span data-stu-id="01cd8-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> button</span></span>|<span data-ttu-id="01cd8-114">基になるデータ ソースに新しい行を挿入します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-114">Inserts a new row into the underlying data source.</span></span>|  
|<span data-ttu-id="01cd8-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> ボタン</span><span class="sxs-lookup"><span data-stu-id="01cd8-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button</span></span>|<span data-ttu-id="01cd8-116">基になるデータ ソースから現在の行を削除します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-116">Deletes the current row from the underlying data source.</span></span>|  
|<span data-ttu-id="01cd8-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> ボタン</span><span class="sxs-lookup"><span data-stu-id="01cd8-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button</span></span>|<span data-ttu-id="01cd8-118">基になるデータ ソースの最初の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-118">Moves to the first item in the underlying data source.</span></span>|  
|<span data-ttu-id="01cd8-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> ボタン</span><span class="sxs-lookup"><span data-stu-id="01cd8-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> button</span></span>|<span data-ttu-id="01cd8-120">基になるデータ ソースの最後の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-120">Moves to the last item in the underlying data source.</span></span>|  
|<span data-ttu-id="01cd8-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> ボタン</span><span class="sxs-lookup"><span data-stu-id="01cd8-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> button</span></span>|<span data-ttu-id="01cd8-122">基になるデータ ソースの次の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-122">Moves to the next item in the underlying data source.</span></span>|  
|<span data-ttu-id="01cd8-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> ボタン</span><span class="sxs-lookup"><span data-stu-id="01cd8-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> button</span></span>|<span data-ttu-id="01cd8-124">基になるデータ ソースの前の項目に移動します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-124">Moves to the previous item in the underlying data source.</span></span>|  
|<span data-ttu-id="01cd8-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> テキスト ボックス</span><span class="sxs-lookup"><span data-stu-id="01cd8-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> text box</span></span>|<span data-ttu-id="01cd8-126">基になるデータ ソース内の現在の位置を返します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-126">Returns the current position within the underlying data source.</span></span>|  
|<span data-ttu-id="01cd8-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A> テキスト ボックス</span><span class="sxs-lookup"><span data-stu-id="01cd8-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A> text box</span></span>|<span data-ttu-id="01cd8-128">基になるデータ ソースの項目の総数を返します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-128">Returns the total number of items in the underlying data source.</span></span>|  
  
 <span data-ttu-id="01cd8-129">このコレクションの各コントロールに対して、同じ機能をプログラムで提供する <xref:System.Windows.Forms.BindingSource> コンポーネントの対応するメンバーが存在します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-129">For each control in this collection, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically provides the same functionality.</span></span> <span data-ttu-id="01cd8-130">たとえば、<xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> ボタンは <xref:System.Windows.Forms.BindingSource> コンポーネントの <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> メソッドに対応し、<xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> ボタンは <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> メソッドに対応します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-130">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span>  
  
 <span data-ttu-id="01cd8-131">既定のボタンがアプリケーションに適していない場合、またはその他の種類の機能をサポートするために追加のボタンを必要とする場合は、独自の <xref:System.Windows.Forms.ToolStrip> ボタンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="01cd8-131">If the default buttons are not suited to your application, or if you require additional buttons to support other types of functionality, you can supply your own <xref:System.Windows.Forms.ToolStrip> buttons.</span></span> <span data-ttu-id="01cd8-132">参照してください[方法。保存、読み込みを追加し、[キャンセル] ボタンを Windows フォーム BindingNavigator コントロール](load-save-and-cancel-bindingnavigator.md)します。</span><span class="sxs-lookup"><span data-stu-id="01cd8-132">Also see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](load-save-and-cancel-bindingnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01cd8-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="01cd8-133">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="01cd8-134">BindingNavigator コントロール</span><span class="sxs-lookup"><span data-stu-id="01cd8-134">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
