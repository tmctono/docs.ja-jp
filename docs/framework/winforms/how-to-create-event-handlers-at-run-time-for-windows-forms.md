---
title: '方法: 実行時にイベントハンドラーを作成する'
description: Visual Studio で Windows フォームデザイナーを使用して、実行時にイベントハンドラーを作成する方法について説明します。 このアクションにより、実行時にイベントハンドラーを接続できます。
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
ms.openlocfilehash: 857076c46377b3276154d9b193d4bbe51841828f
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325811"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="c74d4-104">方法: Windows フォームで実行時にイベント ハンドラーを作成する</span><span class="sxs-lookup"><span data-stu-id="c74d4-104">How to: Create Event Handlers at Run Time for Windows Forms</span></span>

<span data-ttu-id="c74d4-105">Visual Studio の Windows フォームデザイナーを使用してイベントを作成するだけでなく、実行時にイベントハンドラーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c74d4-105">In addition to creating events using the Windows Forms Designer in Visual Studio, you can also create an event handler at run time.</span></span> <span data-ttu-id="c74d4-106">これにより、プログラムが最初に起動したときにイベント ハンドラーを接続する代わりに、コード内に記述されている条件に基づいて、実行時にイベント ハンドラーを接続できます。</span><span class="sxs-lookup"><span data-stu-id="c74d4-106">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>

## <a name="create-an-event-handler-at-run-time"></a><span data-ttu-id="c74d4-107">実行時にイベントハンドラーを作成する</span><span class="sxs-lookup"><span data-stu-id="c74d4-107">Create an event handler at run time</span></span>

1. <span data-ttu-id="c74d4-108">イベントハンドラーを追加するフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="c74d4-108">Open the form that you want to add an event handler to.</span></span>

2. <span data-ttu-id="c74d4-109">処理するイベントに対応するメソッド シグネチャを持つメソッドをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="c74d4-109">Add a method to your form with the method signature for the event that you want to handle.</span></span>

     <span data-ttu-id="c74d4-110">たとえば、コントロールのイベントを処理する場合は、 <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Button> 次のようなメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="c74d4-110">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>

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

3. <span data-ttu-id="c74d4-111">アプリケーションに応じて、イベント ハンドラーにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c74d4-111">Add code to the event handler as appropriate to your application.</span></span>

4. <span data-ttu-id="c74d4-112">イベント ハンドラーをどのフォームまたはコントロールに対して作成するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c74d4-112">Determine which form or control you want to create an event handler for.</span></span>

5. <span data-ttu-id="c74d4-113">フォームのクラスのメソッドに、イベントを処理するためのイベント ハンドラーを指定するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c74d4-113">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="c74d4-114">たとえば、次のコードでは、イベントハンドラーが `button1_Click` コントロールのイベントを処理することを指定してい <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Button> ます。</span><span class="sxs-lookup"><span data-stu-id="c74d4-114">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     <span data-ttu-id="c74d4-115"><xref:System.ComponentModel.EventHandlerList.AddHandler%2A>上の Visual Basic コードで示されているメソッドは、ボタンのクリックイベントハンドラーを確立します。</span><span class="sxs-lookup"><span data-stu-id="c74d4-115">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>

## <a name="see-also"></a><span data-ttu-id="c74d4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c74d4-116">See also</span></span>

- [<span data-ttu-id="c74d4-117">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="c74d4-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="c74d4-118">イベント ハンドラーの概要</span><span class="sxs-lookup"><span data-stu-id="c74d4-118">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="c74d4-119">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c74d4-119">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
