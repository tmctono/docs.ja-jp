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
ms.openlocfilehash: 440086bfd5384fc46aec2997dbdd9937f7a1b65f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964327"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="b7554-102">方法: Windows フォームで実行時にイベント ハンドラーを作成する</span><span class="sxs-lookup"><span data-stu-id="b7554-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>

<span data-ttu-id="b7554-103">Visual Studio の Windows フォームデザイナーを使用してイベントを作成するだけでなく、実行時にイベントハンドラーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b7554-103">In addition to creating events using the Windows Forms Designer in Visual Studio, you can also create an event handler at run time.</span></span> <span data-ttu-id="b7554-104">これにより、プログラムが最初に起動したときにイベント ハンドラーを接続する代わりに、コード内に記述されている条件に基づいて、実行時にイベント ハンドラーを接続できます。</span><span class="sxs-lookup"><span data-stu-id="b7554-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>

## <a name="create-an-event-handler-at-run-time"></a><span data-ttu-id="b7554-105">実行時にイベントハンドラーを作成する</span><span class="sxs-lookup"><span data-stu-id="b7554-105">Create an event handler at run time</span></span>

1. <span data-ttu-id="b7554-106">イベントハンドラーを追加するフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7554-106">Open the form that you want to add an event handler to.</span></span>

2. <span data-ttu-id="b7554-107">処理するイベントに対応するメソッド シグネチャを持つメソッドをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7554-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>

     <span data-ttu-id="b7554-108">たとえば、 <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Button>コントロールのイベントを処理する場合は、次のようなメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7554-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>

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

3. <span data-ttu-id="b7554-109">アプリケーションに応じて、イベント ハンドラーにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7554-109">Add code to the event handler as appropriate to your application.</span></span>

4. <span data-ttu-id="b7554-110">イベント ハンドラーをどのフォームまたはコントロールに対して作成するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7554-110">Determine which form or control you want to create an event handler for.</span></span>

5. <span data-ttu-id="b7554-111">フォームのクラスのメソッドに、イベントを処理するためのイベント ハンドラーを指定するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7554-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="b7554-112">たとえば、次のコードでは、イベントハンドラー `button1_Click`が<xref:System.Windows.Forms.Button>コントロール<xref:System.Windows.Forms.Control.Click>のイベントを処理することを指定しています。</span><span class="sxs-lookup"><span data-stu-id="b7554-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     <span data-ttu-id="b7554-113">上<xref:System.ComponentModel.EventHandlerList.AddHandler%2A>の Visual Basic コードで示されているメソッドは、ボタンのクリックイベントハンドラーを確立します。</span><span class="sxs-lookup"><span data-stu-id="b7554-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7554-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7554-114">See also</span></span>

- [<span data-ttu-id="b7554-115">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="b7554-115">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="b7554-116">イベント ハンドラーの概要</span><span class="sxs-lookup"><span data-stu-id="b7554-116">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="b7554-117">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b7554-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
