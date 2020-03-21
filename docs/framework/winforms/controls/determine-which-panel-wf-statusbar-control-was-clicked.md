---
title: StatusBar コントロールでクリックされたパネルを確認する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182364"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="250a1-102">方法 : Windows フォームの StatusBar コントロールでクリックされたパネルを確認する</span><span class="sxs-lookup"><span data-stu-id="250a1-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="250a1-103">コントロール<xref:System.Windows.Forms.StatusStrip>と<xref:System.Windows.Forms.ToolStripStatusLabel>コントロールは、 コントロールと<xref:System.Windows.Forms.StatusBar><xref:System.Windows.Forms.StatusBarPanel>コントロールに機能を置き換え、追加します。ただし、下位<xref:System.Windows.Forms.StatusBar>互換性<xref:System.Windows.Forms.StatusBarPanel>と将来の使用の両方を目的として、コントロールと コントロールは保持されます。</span><span class="sxs-lookup"><span data-stu-id="250a1-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="250a1-104">ユーザーのクリックに応答するように[StatusBar コントロール](statusbar-control-windows-forms.md)をプログラムするには、イベント内で case<xref:System.Windows.Forms.StatusBar.PanelClick>ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="250a1-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="250a1-105">イベントには、クリックされた<xref:System.Windows.Forms.StatusBarPanel>.</span><span class="sxs-lookup"><span data-stu-id="250a1-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="250a1-106">この参照を使用して、クリックされたパネルのインデックスを判別し、それに応じてプログラムすることができます。</span><span class="sxs-lookup"><span data-stu-id="250a1-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="250a1-107">コントロールの<xref:System.Windows.Forms.StatusBar><xref:System.Windows.Forms.StatusBar.ShowPanels%2A>プロパティが`true`に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="250a1-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="250a1-108">クリックされたパネルを確認するには</span><span class="sxs-lookup"><span data-stu-id="250a1-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="250a1-109"><xref:System.Windows.Forms.StatusBar.PanelClick>イベント ハンドラーで`Select Case`、(Visual Basic の)`switch case`または (Visual C# または Visual C++) ステートメントを使用して、イベント引数でクリックされたパネルのインデックスを調べて、クリックされたパネルを特定します。</span><span class="sxs-lookup"><span data-stu-id="250a1-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="250a1-110">次のコード例では、<xref:System.Windows.Forms.StatusBar>フォーム上、コントロール、および 2 つの`StatusBar1`<xref:System.Windows.Forms.StatusBarPanel>オブジェクト、`StatusBarPanel1`および`StatusBarPanel2`が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="250a1-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     <span data-ttu-id="250a1-111">(ビジュアル C#、ビジュアル C++)フォームのコンストラクターに次のコードを配置して、イベント ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="250a1-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="250a1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="250a1-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="250a1-113">方法 : ステータス バー パネルのサイズを設定する</span><span class="sxs-lookup"><span data-stu-id="250a1-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="250a1-114">チュートリアル : ステータス バー情報の実行時更新</span><span class="sxs-lookup"><span data-stu-id="250a1-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="250a1-115">StatusBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="250a1-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
