---
title: '方法: Windows フォームの DomainUpDown コントロールから項目を削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 0c07365f5be2e419b4049a466949fed2d884d897
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913134"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="c782a-102">方法: Windows フォームの DomainUpDown コントロールから項目を削除する</span><span class="sxs-lookup"><span data-stu-id="c782a-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="c782a-103">項目を削除するには、Windows フォームから<xref:System.Windows.Forms.DomainUpDown>コントロールを呼び出すことによって、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>または<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>のメソッド、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="c782a-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="c782a-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>メソッドは、特定のアイテムを削除中に、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>メソッドは、位置を使用して項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="c782a-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="c782a-105">アイテムを削除するには</span><span class="sxs-lookup"><span data-stu-id="c782a-105">To remove an item</span></span>  
  
-   <span data-ttu-id="c782a-106">使用して、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>のメソッド、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>名前で項目を削除するクラス。</span><span class="sxs-lookup"><span data-stu-id="c782a-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="c782a-107">- または -</span><span class="sxs-lookup"><span data-stu-id="c782a-107">-or-</span></span>  
  
-   <span data-ttu-id="c782a-108">使用して、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>位置を使用して項目を削除するメソッド。</span><span class="sxs-lookup"><span data-stu-id="c782a-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c782a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c782a-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c782a-110">DomainUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="c782a-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="c782a-111">DomainUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="c782a-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
