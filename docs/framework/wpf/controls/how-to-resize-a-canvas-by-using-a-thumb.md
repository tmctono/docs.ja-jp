---
title: '方法: つまみを使用したキャンバスのサイズ変更'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 80b873e81acc243ff61257bc305c4f782b5bf867
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351830"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="28d92-102">方法: つまみを使用したキャンバスのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="28d92-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="28d92-103">この例は、使用する方法を示します、<xref:System.Windows.Controls.Primitives.Thumb>サイズを変更するコントロールを<xref:System.Windows.Controls.Canvas>コントロール。</span><span class="sxs-lookup"><span data-stu-id="28d92-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28d92-104">例</span><span class="sxs-lookup"><span data-stu-id="28d92-104">Example</span></span>  
 <span data-ttu-id="28d92-105"><xref:System.Windows.Controls.Primitives.Thumb>コントロールには、監視することによってコントロールのサイズを変更または移動に使用できるドラッグ機能が用意されています、 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>、<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>と<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>のイベント、<xref:System.Windows.Controls.Primitives.Thumb>します。</span><span class="sxs-lookup"><span data-stu-id="28d92-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="28d92-106">上にマウス ポインターが一時停止すると、マウスの左ボタンを押して、ユーザーがドラッグ操作を開始、<xref:System.Windows.Controls.Primitives.Thumb>コントロール。</span><span class="sxs-lookup"><span data-stu-id="28d92-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="28d92-107">マウスの左ボタンが押されている限り、ドラッグ操作が続行します。</span><span class="sxs-lookup"><span data-stu-id="28d92-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="28d92-108">ドラッグ操作中に、<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>複数回発生することができます。</span><span class="sxs-lookup"><span data-stu-id="28d92-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="28d92-109">これが発生するたびに、<xref:System.Windows.Controls.Primitives.DragDeltaEventArgs>クラスには、マウスの位置の変化に対応する位置の変更が用意されています。</span><span class="sxs-lookup"><span data-stu-id="28d92-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="28d92-110">マウスの左ボタンを離したときに、ドラッグ操作が完了しました。</span><span class="sxs-lookup"><span data-stu-id="28d92-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="28d92-111">ドラッグ操作では、新しい座標のみ提供します自動的に再配置されない、<xref:System.Windows.Controls.Primitives.Thumb>します。</span><span class="sxs-lookup"><span data-stu-id="28d92-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="28d92-112">次の例は、<xref:System.Windows.Controls.Primitives.Thumb>の子要素であるコントロール、<xref:System.Windows.Controls.Canvas>コントロール。</span><span class="sxs-lookup"><span data-stu-id="28d92-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="28d92-113">イベント ハンドラーの<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>イベントに移動するロジックを提供する、<xref:System.Windows.Controls.Primitives.Thumb>サイズを変更して、 <xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="28d92-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="28d92-114">イベント ハンドラー、<xref:System.Windows.Controls.Primitives.Thumb.DragStarted>と<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>の色を変更するイベント、<xref:System.Windows.Controls.Primitives.Thumb>ドラッグ操作中にします。</span><span class="sxs-lookup"><span data-stu-id="28d92-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="28d92-115">次の例では、定義、<xref:System.Windows.Controls.Primitives.Thumb>します。</span><span class="sxs-lookup"><span data-stu-id="28d92-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="28d92-116">次の例は、<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>を移動するイベント ハンドラー、<xref:System.Windows.Controls.Primitives.Thumb>のサイズを変更し、<xref:System.Windows.Controls.Canvas>マウスの動きへの応答。</span><span class="sxs-lookup"><span data-stu-id="28d92-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="28d92-117">次の例は、<xref:System.Windows.Controls.Primitives.Thumb.DragStarted>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="28d92-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="28d92-118">次の例は、<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="28d92-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="28d92-119">サンプル全体については、[Thumb ドラッグ機能のサンプル](https://go.microsoft.com/fwlink/?LinkID=160042)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28d92-119">For the complete sample, see [Thumb Drag Functionality Sample](https://go.microsoft.com/fwlink/?LinkID=160042).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d92-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="28d92-120">See also</span></span>
- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
