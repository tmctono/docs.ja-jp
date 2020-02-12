---
title: '方法: つまみを使用してキャンバスのサイズを変更する'
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
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124300"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="465e6-102">方法: つまみを使用してキャンバスのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="465e6-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="465e6-103">この例では、<xref:System.Windows.Controls.Primitives.Thumb> コントロールを使用して <xref:System.Windows.Controls.Canvas> コントロールのサイズを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="465e6-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="465e6-104">例</span><span class="sxs-lookup"><span data-stu-id="465e6-104">Example</span></span>  
 <span data-ttu-id="465e6-105"><xref:System.Windows.Controls.Primitives.Thumb> コントロールには、<xref:System.Windows.Controls.Primitives.Thumb>の <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>、<xref:System.Windows.Controls.Primitives.Thumb.DragDelta> および <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> イベントを監視することで、コントロールの移動やサイズ変更に使用できるドラッグ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="465e6-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="465e6-106">マウスポインターが <xref:System.Windows.Controls.Primitives.Thumb> コントロールで一時停止しているときにマウスの左ボタンを押すと、ドラッグ操作が開始されます。</span><span class="sxs-lookup"><span data-stu-id="465e6-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="465e6-107">ドラッグ操作は、マウスの左ボタンが押されている間は続行されます。</span><span class="sxs-lookup"><span data-stu-id="465e6-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="465e6-108">ドラッグ操作中に、<xref:System.Windows.Controls.Primitives.Thumb.DragDelta> が複数回発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="465e6-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="465e6-109"><xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> クラスは、発生するたびに、マウス位置の変化に対応する位置の変更を提供します。</span><span class="sxs-lookup"><span data-stu-id="465e6-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="465e6-110">ユーザーがマウスの左ボタンを放すと、ドラッグ操作が終了します。</span><span class="sxs-lookup"><span data-stu-id="465e6-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="465e6-111">ドラッグ操作では、新しい座標のみが提供されます。<xref:System.Windows.Controls.Primitives.Thumb>の位置が自動的に変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="465e6-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="465e6-112">次の例は、<xref:System.Windows.Controls.Canvas> コントロールの子要素である <xref:System.Windows.Controls.Primitives.Thumb> コントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="465e6-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="465e6-113"><xref:System.Windows.Controls.Primitives.Thumb.DragDelta> イベントのイベントハンドラーは、<xref:System.Windows.Controls.Primitives.Thumb> を移動し、<xref:System.Windows.Controls.Canvas>のサイズを変更するためのロジックを提供します。</span><span class="sxs-lookup"><span data-stu-id="465e6-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="465e6-114"><xref:System.Windows.Controls.Primitives.Thumb.DragStarted> イベントと <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> イベントのイベントハンドラーは、ドラッグ操作中に <xref:System.Windows.Controls.Primitives.Thumb> の色を変更します。</span><span class="sxs-lookup"><span data-stu-id="465e6-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="465e6-115">次の例では、<xref:System.Windows.Controls.Primitives.Thumb>を定義します。</span><span class="sxs-lookup"><span data-stu-id="465e6-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="465e6-116">次の例は、マウスの動きに応じて <xref:System.Windows.Controls.Primitives.Thumb> を移動し、<xref:System.Windows.Controls.Canvas> のサイズを変更する <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> イベントハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="465e6-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="465e6-117">次の例は、<xref:System.Windows.Controls.Primitives.Thumb.DragStarted> イベントハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="465e6-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="465e6-118">次の例は、<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> イベントハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="465e6-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="465e6-119">完全なサンプルについては、「 [Thumb ドラッグ機能のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="465e6-119">For the complete sample, see [Thumb Drag Functionality Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465e6-120">参照</span><span class="sxs-lookup"><span data-stu-id="465e6-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
