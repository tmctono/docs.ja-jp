---
title: '方法: コントロールのコレクションに対して実行時にコントロールを追加または削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 369946581847b4bdcf8bc658aeb94b14c529061c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182286"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="0497f-102">方法: コントロールのコレクションに対して実行時にコントロールを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="0497f-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="0497f-103">アプリケーション開発の一般的なタスクは、フォーム上の任意のコンテナー コントロール (または コントロール、<xref:System.Windows.Forms.Panel>フォーム<xref:System.Windows.Forms.GroupBox>自体など) に対してコントロールを追加したり、コントロールを削除したりすることです。</span><span class="sxs-lookup"><span data-stu-id="0497f-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="0497f-104">デザイン時に、コントロールをパネルやグループ ボックスに直接ドラッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="0497f-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="0497f-105">実行時には、これらのコントロールは `Controls` コレクションを保持し、それらにどのコントロールが置かれているかを追跡します。</span><span class="sxs-lookup"><span data-stu-id="0497f-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0497f-106">次のコード例は、コントロールのコレクションを保持する任意のコントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0497f-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="0497f-107">プログラムを使用して、コレクションにコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="0497f-107">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="0497f-108">追加するコントロールのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0497f-108">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="0497f-109">新しいコントロールのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0497f-109">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="0497f-110">親コントロールの `Controls` コレクションにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="0497f-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="0497f-111">コントロールのインスタンスを作成する方法を次のコード例<xref:System.Windows.Forms.Button>に示します。</span><span class="sxs-lookup"><span data-stu-id="0497f-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="0497f-112">コントロールを持つフォームが<xref:System.Windows.Forms.Panel>必要で、作成されるボタンのイベント処理メソッドが`NewPanelButton_Click`既に存在します。</span><span class="sxs-lookup"><span data-stu-id="0497f-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="0497f-113">プログラムを使用してコレクションからコントロールを削除するには</span><span class="sxs-lookup"><span data-stu-id="0497f-113">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="0497f-114">イベントからイベント ハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0497f-114">Remove the event handler from the event.</span></span> <span data-ttu-id="0497f-115">Visual Basic では[、RemoveHandler ステートメント](../../../visual-basic/language-reference/statements/removehandler-statement.md)キーワードを使用します。C# では[、-= 演算子](../../../csharp/language-reference/operators/subtraction-operator.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0497f-115">In Visual Basic, use the [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) keyword; in C#, use the [-= operator](../../../csharp/language-reference/operators/subtraction-operator.md).</span></span>  
  
2. <span data-ttu-id="0497f-116">`Remove` メソッドを使用して、パネルの `Controls` コレクションから目的のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="0497f-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="0497f-117">コントロールで<xref:System.Windows.Forms.Control.Dispose%2A>使用されているすべてのリソースを解放するメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0497f-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0497f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0497f-118">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="0497f-119">Panel コントロール</span><span class="sxs-lookup"><span data-stu-id="0497f-119">Panel Control</span></span>](panel-control-windows-forms.md)
