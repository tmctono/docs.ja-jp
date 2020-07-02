---
title: '方法: 複数のイベントを1つのイベントハンドラーに接続する'
description: C# のプロパティウィンドウのイベントビューを使用して Windows フォームの1つのイベントハンドラーに複数のイベントを接続する方法について説明します。
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
ms.openlocfilehash: cca85c223b46d9a82dbc3e34e3377fb83c075959
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621887"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="002d0-103">方法: Windows フォームの 1 つのイベント ハンドラーに複数のイベントを関連付ける</span><span class="sxs-lookup"><span data-stu-id="002d0-103">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="002d0-104">アプリケーションの設計では、複数のイベントに対して単一のイベントハンドラーを使用するか、複数のイベントで同じ手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="002d0-104">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="002d0-105">たとえば、多くの場合、メニューコマンドで同じ機能を公開すると、フォーム上のボタンと同じイベントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="002d0-105">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="002d0-106">これを行うには、C# のプロパティウィンドウのイベントビューを使用するか、 `Handles` Visual Basic コードエディターで、キーワードと**クラス名**と**メソッド名**のドロップダウンボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="002d0-106">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="002d0-107">複数のイベントを Visual Basic の1つのイベントハンドラーに接続するには</span><span class="sxs-lookup"><span data-stu-id="002d0-107">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="002d0-108">フォームを右クリックし、[**コードの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="002d0-108">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="002d0-109">[**クラス名**] ボックスの一覧で、イベントハンドラーが処理するコントロールの1つを選択します。</span><span class="sxs-lookup"><span data-stu-id="002d0-109">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="002d0-110">[**メソッド名**] ボックスの一覧で、イベントハンドラーが処理するイベントの1つを選択します。</span><span class="sxs-lookup"><span data-stu-id="002d0-110">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="002d0-111">コードエディターによって、適切なイベントハンドラーが挿入され、メソッド内に挿入ポイントが配置されます。</span><span class="sxs-lookup"><span data-stu-id="002d0-111">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="002d0-112">次の例では、 <xref:System.Windows.Forms.Control.Click> コントロールのイベントです <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="002d0-112">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="002d0-113">処理するその他のイベントを句に追加し `Handles` ます。</span><span class="sxs-lookup"><span data-stu-id="002d0-113">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="002d0-114">適切なコードをイベントハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="002d0-114">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="002d0-115">C で複数のイベントを1つのイベントハンドラーに接続するには\#</span><span class="sxs-lookup"><span data-stu-id="002d0-115">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="002d0-116">イベントハンドラーを接続するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="002d0-116">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="002d0-117">プロパティウィンドウで、[**イベント**] ボタン ([![イベント] ボタン](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="002d0-117">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="002d0-118">処理するイベントの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="002d0-118">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="002d0-119">イベント名の横にある [値] セクションで、ドロップダウンボタンをクリックして、処理するイベントのメソッドシグネチャに一致する既存のイベントハンドラーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="002d0-119">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="002d0-120">一覧から適切なイベントハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="002d0-120">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="002d0-121">イベントを既存のイベントハンドラーにバインドするためのコードがフォームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="002d0-121">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002d0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="002d0-122">See also</span></span>

- [<span data-ttu-id="002d0-123">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="002d0-123">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="002d0-124">イベント ハンドラーの概要</span><span class="sxs-lookup"><span data-stu-id="002d0-124">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
