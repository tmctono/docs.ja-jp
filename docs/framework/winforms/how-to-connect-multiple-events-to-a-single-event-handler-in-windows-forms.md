---
title: '方法: 複数のイベントを1つのイベントハンドラーに接続する'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 0591291522ab1da04fef90bf1c0a73cf33ba0518
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739611"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="598c7-102">方法 : Windows フォームの 1 つのイベント ハンドラーに複数のイベントを関連付ける</span><span class="sxs-lookup"><span data-stu-id="598c7-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="598c7-103">アプリケーションの設計では、複数のイベントに対して単一のイベントハンドラーを使用するか、複数のイベントで同じ手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="598c7-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="598c7-104">たとえば、多くの場合、メニューコマンドで同じ機能を公開すると、フォーム上のボタンと同じイベントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="598c7-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="598c7-105">これを行うには、のC#プロパティウィンドウのイベントビューを使用するか、Visual Basic コードエディターで `Handles` キーワードと**クラス名**と**メソッド名**のドロップダウンボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="598c7-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="598c7-106">複数のイベントを Visual Basic の1つのイベントハンドラーに接続するには</span><span class="sxs-lookup"><span data-stu-id="598c7-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="598c7-107">フォームを右クリックし、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="598c7-107">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="598c7-108">**[クラス名]** ボックスの一覧で、イベントハンドラーが処理するコントロールの1つを選択します。</span><span class="sxs-lookup"><span data-stu-id="598c7-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="598c7-109">**[メソッド名]** ボックスの一覧で、イベントハンドラーが処理するイベントの1つを選択します。</span><span class="sxs-lookup"><span data-stu-id="598c7-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="598c7-110">コードエディターによって、適切なイベントハンドラーが挿入され、メソッド内に挿入ポイントが配置されます。</span><span class="sxs-lookup"><span data-stu-id="598c7-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="598c7-111">次の例では、<xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Click> イベントです。</span><span class="sxs-lookup"><span data-stu-id="598c7-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="598c7-112">処理するその他のイベントを `Handles` 句に追加します。</span><span class="sxs-lookup"><span data-stu-id="598c7-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="598c7-113">適切なコードをイベントハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="598c7-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="598c7-114">C\# で1つのイベントハンドラーに複数のイベントを接続するには</span><span class="sxs-lookup"><span data-stu-id="598c7-114">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="598c7-115">イベントハンドラーを接続するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="598c7-115">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="598c7-116">プロパティウィンドウで、 **[イベント]** ボタン ([![イベント] ボタン](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="598c7-116">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="598c7-117">処理するイベントの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="598c7-117">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="598c7-118">イベント名の横にある [値] セクションで、ドロップダウンボタンをクリックして、処理するイベントのメソッドシグネチャに一致する既存のイベントハンドラーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="598c7-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="598c7-119">一覧から適切なイベントハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="598c7-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="598c7-120">イベントを既存のイベントハンドラーにバインドするためのコードがフォームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="598c7-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598c7-121">参照</span><span class="sxs-lookup"><span data-stu-id="598c7-121">See also</span></span>

- [<span data-ttu-id="598c7-122">Windows フォーム内のイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="598c7-122">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="598c7-123">イベント ハンドラーの概要</span><span class="sxs-lookup"><span data-stu-id="598c7-123">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
