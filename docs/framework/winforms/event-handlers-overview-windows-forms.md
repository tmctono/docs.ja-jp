---
title: イベント ハンドラーの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141693"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="0a758-102">イベント ハンドラーの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="0a758-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="0a758-103">イベント ハンドラーは、イベントにバインドされるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="0a758-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="0a758-104">イベントが発生すると、イベント ハンドラー内のコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0a758-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="0a758-105">各イベント ハンドラーには、イベントを適切に処理するための 2 つのパラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0a758-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="0a758-106">コントロールのイベント ハンドラーの例を<xref:System.Windows.Forms.Button>次に<xref:System.Windows.Forms.Control.Click>示します。</span><span class="sxs-lookup"><span data-stu-id="0a758-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="0a758-107">最初のパラメーター`sender`は、イベントを発生させたオブジェクトへの参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="0a758-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="0a758-108">2 番目の`e`パラメータは、上の例では、処理されるイベントに固有のオブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="0a758-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="0a758-109">オブジェクトのプロパティ (および場合によってはメソッド) を参照することにより、マウス イベントのマウスの位置やドラッグ アンド ドロップ イベントで転送されるデータなどの情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0a758-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="0a758-110">通常、各イベントは、2 番目のパラメーターに対して異なるイベント オブジェクト型を持つイベント ハンドラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="0a758-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="0a758-111">イベントと イベントのイベント ハンドラーなど<xref:System.Windows.Forms.Control.MouseDown>、2 番目の<xref:System.Windows.Forms.Control.MouseUp>パラメーターに対して同じオブジェクト型を持つイベント ハンドラーもあります。</span><span class="sxs-lookup"><span data-stu-id="0a758-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="0a758-112">これらの種類のイベントでは、同じイベント ハンドラーを使用して両方のイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="0a758-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="0a758-113">同じイベント ハンドラーを使用して、異なるコントロールに対して同じイベントを処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a758-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="0a758-114">たとえば、フォーム上にコントロールの<xref:System.Windows.Forms.RadioButton>グループがある場合、イベントに対して 1 つのイベント ハンドラーを<xref:System.Windows.Forms.Control.Click>作成し、各コントロールの<xref:System.Windows.Forms.Control.Click>イベントを 1 つのイベント ハンドラーにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="0a758-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="0a758-115">詳細については、「[方法 : Windows フォームで複数のイベントを 1 つのイベント ハンドラに接続する](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a758-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a758-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a758-116">See also</span></span>

- [<span data-ttu-id="0a758-117">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="0a758-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="0a758-118">イベントの概要</span><span class="sxs-lookup"><span data-stu-id="0a758-118">Events Overview</span></span>](events-overview-windows-forms.md)
