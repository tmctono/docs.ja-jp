---
title: '方法: メニュー項目を ContextMenuStrip に追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 534bbd2c2edb68dca0f2a1c2997ff1ba762ef07c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011048"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="7646f-102">方法: メニュー項目を ContextMenuStrip に追加する</span><span class="sxs-lookup"><span data-stu-id="7646f-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="7646f-103">一度に 1 つのメニュー項目または複数の項目を追加することができます、<xref:System.Windows.Forms.ContextMenuStrip>します。</span><span class="sxs-lookup"><span data-stu-id="7646f-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="7646f-104">1 つのメニュー項目を ContextMenuStrip に追加するには</span><span class="sxs-lookup"><span data-stu-id="7646f-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
- <span data-ttu-id="7646f-105">使用して、 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 1 つのメニュー項目を追加する方法、<xref:System.Windows.Forms.ContextMenuStrip>します。</span><span class="sxs-lookup"><span data-stu-id="7646f-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="7646f-106">いくつかのメニュー項目を ContextMenuStrip に追加するには</span><span class="sxs-lookup"><span data-stu-id="7646f-106">To add several menu items to a ContextMenuStrip</span></span>  
  
- <span data-ttu-id="7646f-107">使用して、<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>をいくつかのメニュー項目を追加するメソッドを<xref:System.Windows.Forms.ContextMenuStrip>します。</span><span class="sxs-lookup"><span data-stu-id="7646f-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7646f-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="7646f-108">See also</span></span>

- [<span data-ttu-id="7646f-109">ContextMenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="7646f-109">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
