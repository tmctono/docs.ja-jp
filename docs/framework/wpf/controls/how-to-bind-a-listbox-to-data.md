---
title: '方法: ListBox にデータをバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911158"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="42729-102">方法: ListBox にデータをバインドする</span><span class="sxs-lookup"><span data-stu-id="42729-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="42729-103">アプリケーション開発者が作成できる<xref:System.Windows.Controls.ListBox>それぞれのコンテンツを指定することがなくコントロール<xref:System.Windows.Controls.ListBoxItem>とは別にします。</span><span class="sxs-lookup"><span data-stu-id="42729-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="42729-104">データ バインディングを使用すると、個々 の項目にデータをバインドします。</span><span class="sxs-lookup"><span data-stu-id="42729-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="42729-105">次の例を作成する方法を示しています、<xref:System.Windows.Controls.ListBox>を設定する、<xref:System.Windows.Controls.ListBoxItem>というデータ ソースへのデータ バインディングによって要素*色*します。</span><span class="sxs-lookup"><span data-stu-id="42729-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="42729-106">ここで使用する必要はありません<xref:System.Windows.Controls.ListBoxItem>タグを各項目の内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="42729-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42729-107">例</span><span class="sxs-lookup"><span data-stu-id="42729-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="42729-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="42729-108">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="42729-109">コントロール</span><span class="sxs-lookup"><span data-stu-id="42729-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)
