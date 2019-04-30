---
title: '方法: Windows フォームの 1 つのイベント ハンドラーに複数のイベントを関連付ける'
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
ms.openlocfilehash: eec6a754b885cd169e5542221caefb3233c4c8af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967025"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="51296-102">方法: Windows フォームの 1 つのイベント ハンドラーに複数のイベントを関連付ける</span><span class="sxs-lookup"><span data-stu-id="51296-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="51296-103">アプリケーションの設計でする必要がありますを 1 つのイベント ハンドラーを使用して、複数のイベントまたは複数のイベントが、同じ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51296-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="51296-104">たとえば、フォーム上のボタンの場合は、同じ機能を公開するように、同じイベントを発生させるメニュー コマンドを使用して強力な時間を節約では多くの場合です。</span><span class="sxs-lookup"><span data-stu-id="51296-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="51296-105">[プロパティ] ウィンドウのイベント ビューを使用してこれを行うC#またはを使用して、`Handles`キーワードと**クラス名**と**メソッド名**ドロップダウン ボックスでは、Visual Basic コード エディター。</span><span class="sxs-lookup"><span data-stu-id="51296-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="51296-106">Visual Basic での 1 つのイベント ハンドラーに複数のイベントを接続するには</span><span class="sxs-lookup"><span data-stu-id="51296-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="51296-107">フォームを右クリックし **コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="51296-107">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="51296-108">**クラス名**ドロップダウン ボックスで、イベント ハンドラーが処理するコントロールのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="51296-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="51296-109">**メソッド名**ドロップダウン ボックスで、イベント ハンドラーが処理するイベントは、のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="51296-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="51296-110">コード エディターでは、適切なイベント ハンドラーを挿入し、メソッド内でカーソルを配置します。</span><span class="sxs-lookup"><span data-stu-id="51296-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="51296-111">次の例では、<xref:System.Windows.Forms.Control.Click>イベントを<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="51296-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="51296-112">他のイベントを処理を追加、`Handles`句。</span><span class="sxs-lookup"><span data-stu-id="51296-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="51296-113">イベント ハンドラーに、適切なコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="51296-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="51296-114">C での 1 つのイベント ハンドラーに複数のイベントを接続するには\#</span><span class="sxs-lookup"><span data-stu-id="51296-114">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="51296-115">イベント ハンドラーを接続するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="51296-115">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="51296-116">[プロパティ] ウィンドウ、**イベント**ボタン (![イベント ボタン](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow"))。</span><span class="sxs-lookup"><span data-stu-id="51296-116">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="51296-117">処理するイベントの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51296-117">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="51296-118">イベント名の横の [値] セクションでは、処理するイベントのメソッド シグネチャに一致する既存のイベント ハンドラーの一覧を表示するドロップダウン ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51296-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="51296-119">一覧から適切なイベント ハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="51296-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="51296-120">コードは、既存のイベント ハンドラーにイベントをバインドするフォームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="51296-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51296-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="51296-121">See also</span></span>

- [<span data-ttu-id="51296-122">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="51296-122">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="51296-123">イベント ハンドラーの概要</span><span class="sxs-lookup"><span data-stu-id="51296-123">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
