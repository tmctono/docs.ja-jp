---
title: '方法: Windows フォームのボタン クリックに応答するには'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: e6e6d041422a79171ec4b6159f0789b8aa6a50d5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724987"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="9477d-102">方法: Windows フォームのボタン クリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="9477d-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="9477d-103">Windows フォームの最も基本的な使用<xref:System.Windows.Forms.Button>コントロールのボタンがクリックされたときに、いくつかのコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="9477d-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="9477d-104">クリックすると、<xref:System.Windows.Forms.Button>コントロールもなどが生成されるその他のイベント数、 <xref:System.Windows.Forms.Control.MouseEnter>、 <xref:System.Windows.Forms.Control.MouseDown>、および<xref:System.Windows.Forms.Control.MouseUp>イベント。</span><span class="sxs-lookup"><span data-stu-id="9477d-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="9477d-105">これらの関連イベントのイベント ハンドラーをアタッチする場合は、そのアクションが競合しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9477d-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="9477d-106">たとえば場合、ユーザーがテキスト ボックスに入力した情報をクリア ボタンをクリックして、ボタンの上にマウス ポインターを置く必要があります表示されません現時点で存在しない情報をツール ヒント。</span><span class="sxs-lookup"><span data-stu-id="9477d-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="9477d-107">ユーザーをダブルクリックする場合、<xref:System.Windows.Forms.Button>コントロール、1 回のクリックを個別に処理されます。 これは、コントロールがダブルクリック イベントをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="9477d-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="9477d-108">ボタンのクリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="9477d-108">To respond to a button click</span></span>  
  
-   <span data-ttu-id="9477d-109">ボタンの`Click`<xref:System.EventHandler>を実行するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="9477d-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="9477d-110">`Button1_Click` コントロールにバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9477d-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="9477d-111">詳細については、「[方法 :Windows フォームの実行時にイベント ハンドラーを作成](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)です。</span><span class="sxs-lookup"><span data-stu-id="9477d-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9477d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9477d-112">See also</span></span>
- [<span data-ttu-id="9477d-113">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="9477d-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="9477d-114">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="9477d-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="9477d-115">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="9477d-115">Button Control</span></span>](button-control-windows-forms.md)
