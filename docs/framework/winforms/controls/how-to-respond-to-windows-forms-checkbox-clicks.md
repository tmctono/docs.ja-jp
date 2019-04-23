---
title: '方法: Windows フォーム CheckBox のクリックに応答する'
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
ms.openlocfilehash: ce616f45ceaa3db117c6981d2987ac09bba7b3fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319899"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="f655b-102">方法: Windows フォーム CheckBox のクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="f655b-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="f655b-103">ユーザーが Windows フォームをクリックするたびに<xref:System.Windows.Forms.CheckBox>コントロール、<xref:System.Windows.Forms.Control.Click>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="f655b-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="f655b-104">チェック ボックスの状態に応じていくつかの操作を実行するアプリケーションをプログラミングできます。</span><span class="sxs-lookup"><span data-stu-id="f655b-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="f655b-105">CheckBox のクリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="f655b-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="f655b-106"><xref:System.Windows.Forms.Control.Click>イベント ハンドラーを使用して、<xref:System.Windows.Forms.CheckBox.Checked%2A>プロパティをコントロールの状態を確認し、必要なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f655b-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    >  <span data-ttu-id="f655b-107">ユーザーをダブルクリックする場合、<xref:System.Windows.Forms.CheckBox>コントロール、1 回のクリックを個別に処理されます。 つまり、<xref:System.Windows.Forms.CheckBox>コントロールは、ダブルクリック イベントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f655b-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f655b-108">ときに、<xref:System.Windows.Forms.CheckBox.AutoCheck%2A>プロパティは`true`(既定)、<xref:System.Windows.Forms.CheckBox>が自動的に選択されているかがクリックされたときにクリアします。</span><span class="sxs-lookup"><span data-stu-id="f655b-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="f655b-109">それ以外の場合、手動で設定する必要あります、<xref:System.Windows.Forms.CheckBox.Checked%2A>プロパティと、<xref:System.Windows.Forms.Control.Click>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="f655b-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="f655b-110">使用することも、<xref:System.Windows.Forms.CheckBox>一連の措置を決定するコントロール。</span><span class="sxs-lookup"><span data-stu-id="f655b-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="f655b-111">操作のチェック ボックスを決定するには、がクリックされます。</span><span class="sxs-lookup"><span data-stu-id="f655b-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="f655b-112">値をクエリする case ステートメントを使用して、<xref:System.Windows.Forms.CheckBox.CheckState%2A>プロパティを一連の措置を決定します。</span><span class="sxs-lookup"><span data-stu-id="f655b-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="f655b-113">ときに、<xref:System.Windows.Forms.CheckBox.ThreeState%2A>プロパティに設定されて`true`、<xref:System.Windows.Forms.CheckBox.CheckState%2A>プロパティは、チェック ボックスを表す 3 つの値を返す可能性があります ボックスがオフの場合、またはサードパーティ中間状態、ボックスが表示されます、淡色表示に外観をオプションを示すためには、ご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="f655b-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    >  <span data-ttu-id="f655b-114">ときに、<xref:System.Windows.Forms.CheckBox.ThreeState%2A>プロパティに設定されて`true`、<xref:System.Windows.Forms.CheckBox.Checked%2A>プロパティが返す`true`両方の<xref:System.Windows.Forms.CheckState.Checked>と<xref:System.Windows.Forms.CheckState.Indeterminate>します。</span><span class="sxs-lookup"><span data-stu-id="f655b-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f655b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f655b-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="f655b-116">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f655b-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="f655b-117">方法: Windows フォームの CheckBox コントロールでオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="f655b-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="f655b-118">CheckBox コントロール</span><span class="sxs-lookup"><span data-stu-id="f655b-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
