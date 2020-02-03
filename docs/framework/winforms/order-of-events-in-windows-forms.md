---
title: イベントの順序
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: 618ac5a6a6a32ae1a53fc60ac80700d7648c81a7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734862"
---
# <a name="order-of-events-in-windows-forms"></a><span data-ttu-id="568ec-102">Windows フォームのイベントの順序</span><span class="sxs-lookup"><span data-stu-id="568ec-102">Order of Events in Windows Forms</span></span>
<span data-ttu-id="568ec-103">Windows フォーム アプリケーションでイベントが発生する順序は、各イベントを順番に処理する必要がある開発者にとって重要な問題です。</span><span class="sxs-lookup"><span data-stu-id="568ec-103">The order in which events are raised in Windows Forms applications is of particular interest to developers concerned with handling each of these events in turn.</span></span> <span data-ttu-id="568ec-104">フォームの構成要素を再描画するときなど、イベント処理に細心の注意が必要な状況では、実行時におけるイベントの正確な発生順序に気を配る必要があります。</span><span class="sxs-lookup"><span data-stu-id="568ec-104">When a situation calls for meticulous handling of events, such as when you are redrawing parts of the form, an awareness of the precise order in which events are raised at run time is necessary.</span></span> <span data-ttu-id="568ec-105">このトピックでは、アプリケーションとコントロールの有効期間におけるいくつかの重要な段階での、イベントの順序について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="568ec-105">This topic provides some details on the order of events during several important stages in the lifetime of applications and controls.</span></span> <span data-ttu-id="568ec-106">マウス入力イベントの順序の詳細については、「 [Windows フォームのマウスイベント](mouse-events-in-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568ec-106">For specific details about the order of mouse input events, see [Mouse Events in Windows Forms](mouse-events-in-windows-forms.md).</span></span> <span data-ttu-id="568ec-107">Windows フォームのイベントの概要については、「[イベントの概要](events-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568ec-107">For an overview of events in Windows Forms, see [Events Overview](events-overview-windows-forms.md).</span></span> <span data-ttu-id="568ec-108">イベントハンドラーの詳細については、「[イベントハンドラーの概要](event-handlers-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568ec-108">For details about the makeup of event handlers, see [Event Handlers Overview](event-handlers-overview-windows-forms.md).</span></span>  
  
## <a name="application-startup-and-shutdown-events"></a><span data-ttu-id="568ec-109">アプリケーションのスタートアップ イベントとシャットダウン イベント。</span><span class="sxs-lookup"><span data-stu-id="568ec-109">Application Startup and Shutdown Events</span></span>  
 <span data-ttu-id="568ec-110"><xref:System.Windows.Forms.Form> クラスおよび <xref:System.Windows.Forms.Control> クラスは、アプリケーションのスタートアップおよびシャットダウンに関連する一連のイベントを公開しています。</span><span class="sxs-lookup"><span data-stu-id="568ec-110">The <xref:System.Windows.Forms.Form> and <xref:System.Windows.Forms.Control> classes expose a set of events related to application startup and shutdown.</span></span> <span data-ttu-id="568ec-111">Windows フォーム アプリケーションが起動すると、メイン フォームのスタートアップ イベントが次の順序で発生します。</span><span class="sxs-lookup"><span data-stu-id="568ec-111">When a Windows Forms application starts, the startup events of the main form are raised in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 <span data-ttu-id="568ec-112">アプリケーションを閉じると、メイン フォームのシャットダウン イベントが次の順序で発生します。</span><span class="sxs-lookup"><span data-stu-id="568ec-112">When an application closes, the shutdown events of the main form are raised in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 <span data-ttu-id="568ec-113"><xref:System.Windows.Forms.Application.ApplicationExit> クラスの <xref:System.Windows.Forms.Application> イベントは、メイン フォームのシャットダウン イベントの後に発生します。</span><span class="sxs-lookup"><span data-stu-id="568ec-113">The <xref:System.Windows.Forms.Application.ApplicationExit> event of the <xref:System.Windows.Forms.Application> class is raised after the shutdown events of the main form.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="568ec-114">Visual Basic 2005 には、追加のアプリケーション イベント (<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> や <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType> など) があります。</span><span class="sxs-lookup"><span data-stu-id="568ec-114">Visual Basic 2005 includes additional application events, such as <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> and <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span></span>  
  
## <a name="focus-and-validation-events"></a><span data-ttu-id="568ec-115">フォーカス イベントと検証イベント</span><span class="sxs-lookup"><span data-stu-id="568ec-115">Focus and Validation Events</span></span>  
 <span data-ttu-id="568ec-116">キーボード (Tab、Shift + Tab など) を使用するか、<xref:System.Windows.Forms.Control.Select%2A> メソッドまたは <xref:System.Windows.Forms.Control.SelectNextControl%2A> メソッドを呼び出すか、<xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> プロパティを現在のフォームに設定してフォーカスを変更すると、次の順序で <xref:System.Windows.Forms.Control> クラスのフォーカス イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="568ec-116">When you change the focus by using the keyboard (TAB, SHIFT+TAB, and so on), by calling the <xref:System.Windows.Forms.Control.Select%2A> or <xref:System.Windows.Forms.Control.SelectNextControl%2A> methods, or by setting the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property to the current form, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
 <span data-ttu-id="568ec-117">マウスの使用、または <xref:System.Windows.Forms.Control.Focus%2A> メソッドの呼び出しによってフォーカスを変更すると、次の順序で <xref:System.Windows.Forms.Control> クラスのフォーカス イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="568ec-117">When you change the focus by using the mouse or by calling the <xref:System.Windows.Forms.Control.Focus%2A> method, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a><span data-ttu-id="568ec-118">参照</span><span class="sxs-lookup"><span data-stu-id="568ec-118">See also</span></span>

- [<span data-ttu-id="568ec-119">Windows フォーム内のイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="568ec-119">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
