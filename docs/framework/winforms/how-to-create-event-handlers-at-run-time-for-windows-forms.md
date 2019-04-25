---
title: '方法: Windows フォームで実行時にイベント ハンドラーを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 09f090c6267093e3ad59266d8c77ea13b13b63d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801583"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="11798-102">方法: Windows フォームで実行時にイベント ハンドラーを作成する</span><span class="sxs-lookup"><span data-stu-id="11798-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>
<span data-ttu-id="11798-103">Windows フォーム デザイナーを使用してイベント ハンドラーを作成する他に、実行時にもイベント ハンドラーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="11798-103">In addition to creating events using the Windows Forms Designer, you can also create an event handler at run time.</span></span> <span data-ttu-id="11798-104">これにより、プログラムが最初に起動したときにイベント ハンドラーを接続する代わりに、コード内に記述されている条件に基づいて、実行時にイベント ハンドラーを接続できます。</span><span class="sxs-lookup"><span data-stu-id="11798-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>  
  
### <a name="to-create-an-event-handler-at-run-time"></a><span data-ttu-id="11798-105">実行時にイベント ハンドラーを作成するには</span><span class="sxs-lookup"><span data-stu-id="11798-105">To create an event handler at run time</span></span>  
  
1. <span data-ttu-id="11798-106">コード エディターで、イベント ハンドラーを追加するフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="11798-106">Open the form in the Code Editor that you want to add an event handler to.</span></span>  
  
2. <span data-ttu-id="11798-107">処理するイベントに対応するメソッド シグネチャを持つメソッドをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="11798-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>  
  
     <span data-ttu-id="11798-108">処理された場合など、<xref:System.Windows.Forms.Control.Click>のイベントを<xref:System.Windows.Forms.Button>コントロールでは、次のようメソッドを作成すると。</span><span class="sxs-lookup"><span data-stu-id="11798-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3. <span data-ttu-id="11798-109">アプリケーションに応じて、イベント ハンドラーにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="11798-109">Add code to the event handler as appropriate to your application.</span></span>  
  
4. <span data-ttu-id="11798-110">イベント ハンドラーをどのフォームまたはコントロールに対して作成するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="11798-110">Determine which form or control you want to create an event handler for.</span></span>  
  
5. <span data-ttu-id="11798-111">フォームのクラスのメソッドに、イベントを処理するためのイベント ハンドラーを指定するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="11798-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="11798-112">たとえば、次のコードには、イベント ハンドラーを指定します。`button1_Click`ハンドル、<xref:System.Windows.Forms.Control.Click>のイベントを<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="11798-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="11798-113"><xref:System.ComponentModel.EventHandlerList.AddHandler%2A>上の Visual Basic コードに示すメソッドは、ボタンの click イベント ハンドラーを確立します。</span><span class="sxs-lookup"><span data-stu-id="11798-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11798-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="11798-114">See also</span></span>

- [<span data-ttu-id="11798-115">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="11798-115">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="11798-116">イベント ハンドラーの概要</span><span class="sxs-lookup"><span data-stu-id="11798-116">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="11798-117">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="11798-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
