---
title: コントロール内のイベント
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: c60713917b9c84aa7fad50fb1c81fc9252149ad6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745755"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="7ccfc-102">Windows フォーム コントロールのイベント</span><span class="sxs-lookup"><span data-stu-id="7ccfc-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="7ccfc-103">Windows フォームコントロールは、<xref:System.Windows.Forms.Control?displayProperty=nameWithType>から60を超えるイベントを継承します。</span><span class="sxs-lookup"><span data-stu-id="7ccfc-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7ccfc-104">このようなイベントには、コントロールが描画される原因となる <xref:System.Windows.Forms.Control.Paint> イベント、<xref:System.Windows.Forms.Control.Resize> と <xref:System.Windows.Forms.Control.Layout> イベント、低レベルのマウスおよびキーボードイベントなどのウィンドウの表示に関連するイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ccfc-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="7ccfc-105">一部の下位レベルのイベントは、<xref:System.Windows.Forms.Control> によって <xref:System.Windows.Forms.Control.Click> や <xref:System.Windows.Forms.Control.DoubleClick>などのセマンティックイベントに合成されます。</span><span class="sxs-lookup"><span data-stu-id="7ccfc-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="7ccfc-106">継承されたイベントの詳細については、「<xref:System.Windows.Forms.Control>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ccfc-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="7ccfc-107">継承されたイベントの機能をカスタム コントロールでオーバーライドする必要がある場合、デリゲートを結び付けるのではなく、継承された `On`*EventName* メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="7ccfc-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="7ccfc-108">.NET Framework でのイベント モデルに詳しくない場合は、「[コンポーネントからのイベントの生成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ccfc-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ccfc-109">参照</span><span class="sxs-lookup"><span data-stu-id="7ccfc-109">See also</span></span>

- [<span data-ttu-id="7ccfc-110">OnPaint メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="7ccfc-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="7ccfc-111">ユーザーの入力の処理</span><span class="sxs-lookup"><span data-stu-id="7ccfc-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="7ccfc-112">イベントの定義</span><span class="sxs-lookup"><span data-stu-id="7ccfc-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="7ccfc-113">イベント</span><span class="sxs-lookup"><span data-stu-id="7ccfc-113">Events</span></span>](../../../standard/events/index.md)
