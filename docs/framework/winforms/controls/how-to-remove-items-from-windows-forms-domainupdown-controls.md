---
title: DomainUpDown コントロールからの項目の削除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735770"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="b8a76-102">方法 : Windows フォームの DomainUpDown コントロールから項目を削除する</span><span class="sxs-lookup"><span data-stu-id="b8a76-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="b8a76-103"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> クラスの <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> または <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> メソッドを呼び出すことによって、Windows フォーム <xref:System.Windows.Forms.DomainUpDown> コントロールから項目を削除できます。</span><span class="sxs-lookup"><span data-stu-id="b8a76-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="b8a76-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> メソッドは、特定の項目を削除し、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> メソッドはその位置によって項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="b8a76-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="b8a76-105">アイテムを削除するには</span><span class="sxs-lookup"><span data-stu-id="b8a76-105">To remove an item</span></span>  
  
- <span data-ttu-id="b8a76-106"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> クラスの <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> メソッドを使用して、名前を指定して項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="b8a76-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="b8a76-107">-または-</span><span class="sxs-lookup"><span data-stu-id="b8a76-107">-or-</span></span>  
  
- <span data-ttu-id="b8a76-108">位置によって項目を削除するには、<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8a76-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b8a76-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8a76-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b8a76-110">DomainUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="b8a76-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="b8a76-111">DomainUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="b8a76-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
