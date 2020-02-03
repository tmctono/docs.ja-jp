---
title: CheckBox コントロールでオプションを設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 84198eab42aa02b1bb37fa16a3c4247a37f58a10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746770"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="43635-102">方法 : Windows フォームの CheckBox コントロールでオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="43635-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="43635-103">Windows フォーム <xref:System.Windows.Forms.CheckBox> コントロールは、ユーザーに True/False または Yes/No オプションを提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="43635-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="43635-104">コントロールが選択されると、そのコントロールにチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43635-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="43635-105">CheckBox コントロールを使用してオプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="43635-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="43635-106"><xref:System.Windows.Forms.CheckBox.Checked%2A> プロパティの値を調べてその状態を確認し、その値を使用してオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="43635-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="43635-107">次のコードサンプルでは、<xref:System.Windows.Forms.CheckBox> コントロールの <xref:System.Windows.Forms.CheckBox.CheckedChanged> イベントが発生すると、このチェックボックスがオンになっている場合、フォームの <xref:System.Windows.Forms.Control.AllowDrop%2A> プロパティが `false` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="43635-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="43635-108">これは、ユーザーの操作を制限する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="43635-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="43635-109">参照</span><span class="sxs-lookup"><span data-stu-id="43635-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="43635-110">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="43635-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="43635-111">方法: Windows フォームの CheckBox のクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="43635-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="43635-112">CheckBox コントロール</span><span class="sxs-lookup"><span data-stu-id="43635-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
