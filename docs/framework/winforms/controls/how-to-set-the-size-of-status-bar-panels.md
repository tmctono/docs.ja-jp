---
title: '方法: ステータス バー パネルのサイズを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: efd3074aaf018e7226c484061cbacb2eac0be820
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311904"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a><span data-ttu-id="fe890-102">方法: ステータス バー パネルのサイズを設定する</span><span class="sxs-lookup"><span data-stu-id="fe890-102">How to: Set the Size of Status-Bar Panels</span></span>
> [!NOTE]
>  <span data-ttu-id="fe890-103"><xref:System.Windows.Forms.ToolStripStatusLabel> コントロールは、<xref:System.Windows.Forms.StatusBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.StatusBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe890-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="fe890-104">各インスタンス、<xref:System.Windows.Forms.StatusBarPanel>クラス内で、 [StatusBar コントロール](statusbar-control-windows-forms.md)コントロールにさまざまな動的プロパティは、幅を特定し、実行時の動作のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="fe890-104">Each instance of the <xref:System.Windows.Forms.StatusBarPanel> class within a [StatusBar Control](statusbar-control-windows-forms.md) control has a number of dynamic properties that determine its width and resize behavior at run time.</span></span>  
  
### <a name="to-set-the-size-of-a-panel"></a><span data-ttu-id="fe890-105">パネルのサイズを設定するには</span><span class="sxs-lookup"><span data-stu-id="fe890-105">To set the size of a panel</span></span>  
  
1. <span data-ttu-id="fe890-106">プロシージャでは、次のように設定します。、 <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>、 <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>、と<xref:System.Windows.Forms.StatusBarPanel.Width%2A>プロパティ (または任意のサブセット内) のインデックスを使用するパネルが通過ステータス バーの、<xref:System.Windows.Forms.StatusBar.Panels%2A>のプロパティ、<xref:System.Windows.Forms.StatusBarPanel>コレクション。</span><span class="sxs-lookup"><span data-stu-id="fe890-106">In a procedure, set the <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, and <xref:System.Windows.Forms.StatusBarPanel.Width%2A> properties (or any subset therein) for the status-bar panels using their index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property of the <xref:System.Windows.Forms.StatusBarPanel> collection.</span></span>  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fe890-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe890-107">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="fe890-108">チュートリアル: 実行時にステータス バー情報の更新</span><span class="sxs-lookup"><span data-stu-id="fe890-108">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="fe890-109">方法: Windows フォームの StatusBar コントロール パネルのクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe890-109">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="fe890-110">StatusBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="fe890-110">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
