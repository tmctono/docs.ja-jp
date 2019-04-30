---
title: '方法: (Visual Basic) がブロックされないようにするカスタム イベントを宣言します。'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 6eea47ea2c8aee697eb34ca904dad22ca88e6ce4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051898"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="86d95-102">方法: (Visual Basic) がブロックされないようにするカスタム イベントを宣言します。</span><span class="sxs-lookup"><span data-stu-id="86d95-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="86d95-103">その 1 つのイベント ハンドラーが後続のイベント ハンドラーをブロックしない必要がある場合は、いくつかの状況にがあります。</span><span class="sxs-lookup"><span data-stu-id="86d95-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="86d95-104">カスタム イベントは、そのイベント ハンドラーを非同期的に呼び出すイベントを許可します。</span><span class="sxs-lookup"><span data-stu-id="86d95-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="86d95-105">既定では、イベントの宣言のバッキング ストア フィールドは、すべてのイベント ハンドラーを順番に結合するマルチキャスト デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="86d95-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="86d95-106">つまり、1 つのハンドラーが完了に長時間を受け取る場合、ブロック、その他のハンドラーが完了するまで。</span><span class="sxs-lookup"><span data-stu-id="86d95-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="86d95-107">(正常に動作するイベント ハンドラーは、時間のかかるまたはブロックしている可能性がある操作を実行する必要があることはありません)。</span><span class="sxs-lookup"><span data-stu-id="86d95-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="86d95-108">Visual Basic ではイベントの既定の実装を使用する代わりに、イベント ハンドラーを非同期的に実行するのにカスタム イベントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="86d95-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86d95-109">例</span><span class="sxs-lookup"><span data-stu-id="86d95-109">Example</span></span>  
 <span data-ttu-id="86d95-110">この例で、`AddHandler`アクセサーの各ハンドラーのデリゲートの追加、`Click`イベントを<xref:System.Collections.ArrayList>に格納されている、`EventHandlerList`フィールド。</span><span class="sxs-lookup"><span data-stu-id="86d95-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="86d95-111">コードが発生の場合、`Click`イベント、`RaiseEvent`アクセサーが非同期的を使用してすべてのイベント ハンドラー デリゲートを呼び出す、<xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="86d95-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="86d95-112">そのメソッドでは、ワーカー スレッドで各ハンドラーが呼び出され、ハンドラーは、互いをブロックできませんので、すぐに返します。</span><span class="sxs-lookup"><span data-stu-id="86d95-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="86d95-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="86d95-113">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="86d95-114">イベント</span><span class="sxs-lookup"><span data-stu-id="86d95-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="86d95-115">方法: カスタム イベントを宣言してメモリを節約する</span><span class="sxs-lookup"><span data-stu-id="86d95-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
