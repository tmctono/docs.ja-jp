---
title: '方法 : クリックされた TreeView ノードを判別する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: 7a0e2b69bbec0eb03d40bee2c8e2d4bc9c3558f9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742014"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="2e657-102">方法 : クリックされた TreeView ノード (Windows フォーム) を判別する</span><span class="sxs-lookup"><span data-stu-id="2e657-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="2e657-103">Windows フォーム <xref:System.Windows.Forms.TreeView> コントロールを使用する場合の一般的なタスクは、どのノードがクリックされたかを判断し、適切に対応することです。</span><span class="sxs-lookup"><span data-stu-id="2e657-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="2e657-104">クリックされた TreeView ノードを確認するには</span><span class="sxs-lookup"><span data-stu-id="2e657-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="2e657-105"><xref:System.EventArgs> オブジェクトを使用して、クリックされたノードオブジェクトへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="2e657-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="2e657-106">イベントに関連するデータを含む <xref:System.Windows.Forms.TreeViewEventArgs> クラスを確認して、どのノードがクリックされたかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2e657-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="2e657-107">別の方法として、<xref:System.Windows.Forms.Control.MouseDown> または <xref:System.Windows.Forms.Control.MouseUp> イベントの <xref:System.Windows.Forms.MouseEventArgs> を使用して、クリックが発生した <xref:System.Drawing.Point.Y%2A> の <xref:System.Drawing.Point.X%2A> と <xref:System.Drawing.Point> の座標値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e657-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="2e657-108">次に、<xref:System.Windows.Forms.TreeView> コントロールの <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> メソッドを使用して、どのノードがクリックされたかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2e657-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e657-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e657-109">See also</span></span>

- [<span data-ttu-id="2e657-110">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="2e657-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
