---
title: '方法: キー付きコレクションにアクセスする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 717ba9cc8605da08701de1bd13d6bc6da1c9b758
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739616"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="21d9c-102">方法 : Windows フォームのコレクションにアクセス キーを指定する</span><span class="sxs-lookup"><span data-stu-id="21d9c-102">How to: Access Keyed Collections in Windows Forms</span></span>

- <span data-ttu-id="21d9c-103">個々のコレクションアイテムには、キーでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="21d9c-103">You can access individual collection items by key.</span></span> <span data-ttu-id="21d9c-104">この機能は、通常 Windows フォームアプリケーションで使用される多くのコレクションクラスに追加されています。</span><span class="sxs-lookup"><span data-stu-id="21d9c-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="21d9c-105">次の一覧は、アクセス可能なキー付きコレクションを持つコレクションクラスの一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="21d9c-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="21d9c-106">コレクション内の項目に関連付けられているキーは、通常、項目の名前です。</span><span class="sxs-lookup"><span data-stu-id="21d9c-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="21d9c-107">次の手順では、コレクションクラスを使用して一般的なタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21d9c-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="21d9c-108">コントロールコレクション内の入れ子になったコントロールを検索してフォーカスを与えるには</span><span class="sxs-lookup"><span data-stu-id="21d9c-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="21d9c-109"><xref:System.Windows.Forms.Control.ControlCollection.Find%2A> メソッドと <xref:System.Windows.Forms.Control.Focus%2A> メソッドを使用して、検索してフォーカスを与えるコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="21d9c-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="21d9c-110">イメージコレクション内のイメージにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="21d9c-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="21d9c-111">アクセスするイメージの名前を指定するには、<xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="21d9c-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="21d9c-112">タブページを選択したタブとして設定するには</span><span class="sxs-lookup"><span data-stu-id="21d9c-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="21d9c-113"><xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> プロパティと共に <xref:System.Windows.Forms.TabControl.SelectedTab%2A> プロパティを使用して、選択したタブとして設定するタブページの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="21d9c-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="21d9c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="21d9c-114">See also</span></span>

- [<span data-ttu-id="21d9c-115">Windows フォームについて</span><span class="sxs-lookup"><span data-stu-id="21d9c-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="21d9c-116">方法: Windows フォームの ImageList コンポーネントにイメージを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="21d9c-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
