---
title: '方法: Windows フォームの CheckBox コントロールでオプションを設定する'
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
ms.openlocfilehash: 881996563acef36a1981ca6236c155b8fc56ef0a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307321"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="b7e95-102">方法: Windows フォームの CheckBox コントロールでオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="b7e95-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="b7e95-103">Windows フォーム<xref:System.Windows.Forms.CheckBox>コントロールは、True または False のユーザーに付与するために使用またははい/いいえオプションします。</span><span class="sxs-lookup"><span data-stu-id="b7e95-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="b7e95-104">コントロールが選択されているときに、チェック マークを表示します。</span><span class="sxs-lookup"><span data-stu-id="b7e95-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="b7e95-105">CheckBox コントロールでオプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="b7e95-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="b7e95-106">値を調べて、<xref:System.Windows.Forms.CheckBox.Checked%2A>状態を判断およびその値を使用してオプションを設定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b7e95-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="b7e95-107">以下、ときにコード サンプルでは、<xref:System.Windows.Forms.CheckBox>コントロールの<xref:System.Windows.Forms.CheckBox.CheckedChanged>イベントが発生すると、フォームの<xref:System.Windows.Forms.Control.AllowDrop%2A>プロパティに設定されて`false`チェック ボックスをオンにした場合。</span><span class="sxs-lookup"><span data-stu-id="b7e95-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="b7e95-108">これは、ユーザーの操作を制限する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="b7e95-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7e95-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7e95-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="b7e95-110">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="b7e95-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="b7e95-111">方法: Windows フォーム CheckBox のクリックに応答します。</span><span class="sxs-lookup"><span data-stu-id="b7e95-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="b7e95-112">CheckBox コントロール</span><span class="sxs-lookup"><span data-stu-id="b7e95-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
