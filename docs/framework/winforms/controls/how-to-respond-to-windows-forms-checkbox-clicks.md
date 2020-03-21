---
title: CheckBox のクリックに応答する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: 6ff20c443519446d3804b325924cb3c5cbedea97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141927"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="6fc92-102">方法 : Windows フォーム CheckBox のクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="6fc92-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="6fc92-103">ユーザーが Windows フォーム<xref:System.Windows.Forms.CheckBox>コントロールをクリックすると<xref:System.Windows.Forms.Control.Click>、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="6fc92-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="6fc92-104">チェック ボックスの状態に応じて、何らかのアクションを実行するようにアプリケーションをプログラムできます。</span><span class="sxs-lookup"><span data-stu-id="6fc92-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="6fc92-105">チェック ボックスのクリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="6fc92-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="6fc92-106">イベント<xref:System.Windows.Forms.Control.Click>ハンドラーで、プロパティを<xref:System.Windows.Forms.CheckBox.Checked%2A>使用してコントロールの状態を確認し、必要なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="6fc92-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="6fc92-107">ユーザーが<xref:System.Windows.Forms.CheckBox>コントロールをダブルクリックしようとすると、各クリックが個別に処理されます。つまり、<xref:System.Windows.Forms.CheckBox>コントロールはダブルクリック イベントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6fc92-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6fc92-108">プロパティが<xref:System.Windows.Forms.CheckBox.AutoCheck%2A>`true`(既定値) の場合<xref:System.Windows.Forms.CheckBox>は、 がクリックされると、自動的に選択または選択解除されます。</span><span class="sxs-lookup"><span data-stu-id="6fc92-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="6fc92-109">それ以外の場合は、イベント<xref:System.Windows.Forms.CheckBox.Checked%2A>が発生したときに<xref:System.Windows.Forms.Control.Click>プロパティを手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fc92-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="6fc92-110">コントロールを<xref:System.Windows.Forms.CheckBox>使用して、アクションの一覧を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fc92-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="6fc92-111">チェック ボックスがクリックされたときにアクションのコースを決定するには</span><span class="sxs-lookup"><span data-stu-id="6fc92-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="6fc92-112">case ステートメントを使用して、プロパティの値<xref:System.Windows.Forms.CheckBox.CheckState%2A>を照会してアクションの一覧を決定します。</span><span class="sxs-lookup"><span data-stu-id="6fc92-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="6fc92-113">プロパティが<xref:System.Windows.Forms.CheckBox.ThreeState%2A>に`true`設定されている場合、<xref:System.Windows.Forms.CheckBox.CheckState%2A>このプロパティは、チェック ボックス、チェックボックスの選択解除、またはオプションが使用できないことを示す淡色表示でボックスが表示される 3 番目の不確定状態を表す 3 つの可能な値を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="6fc92-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="6fc92-114">プロパティが<xref:System.Windows.Forms.CheckBox.ThreeState%2A>に`true`設定されている場合、<xref:System.Windows.Forms.CheckBox.Checked%2A>プロパティは`true`、<xref:System.Windows.Forms.CheckState.Checked>と<xref:System.Windows.Forms.CheckState.Indeterminate>の両方に対して返されます。</span><span class="sxs-lookup"><span data-stu-id="6fc92-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc92-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fc92-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="6fc92-116">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6fc92-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="6fc92-117">方法 : Windows フォームの CheckBox コントロールでオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="6fc92-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="6fc92-118">チェック ボックス コントロール</span><span class="sxs-lookup"><span data-stu-id="6fc92-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
