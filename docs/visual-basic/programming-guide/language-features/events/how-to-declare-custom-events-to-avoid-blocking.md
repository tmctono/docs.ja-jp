---
title: '方法: カスタム イベントを宣言してブロックを回避する'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 8d73d9c4590afb33e7176f647069cafcb3a9d7d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345147"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="77660-102">方法: カスタム イベントを宣言してブロックを回避する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77660-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="77660-103">1つのイベントハンドラーが後続のイベントハンドラーをブロックしないようにすることが重要な状況がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="77660-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="77660-104">カスタムイベントを使用すると、イベントでイベントハンドラーを非同期に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="77660-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="77660-105">既定では、イベント宣言のバッキングストアフィールドは、すべてのイベントハンドラーを順番に結合するマルチキャストデリゲートです。</span><span class="sxs-lookup"><span data-stu-id="77660-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="77660-106">これは、1つのハンドラーの完了に時間がかかる場合、完了するまで他のハンドラーがブロックされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="77660-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="77660-107">(適切に動作するイベントハンドラーでは、時間がかかるか、ブロックする可能性のある操作を実行しないでください)。</span><span class="sxs-lookup"><span data-stu-id="77660-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="77660-108">によって提供さ Visual Basic イベントの既定の実装を使用する代わりに、カスタムイベントを使用してイベントハンドラーを非同期的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="77660-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77660-109">例</span><span class="sxs-lookup"><span data-stu-id="77660-109">Example</span></span>  
 <span data-ttu-id="77660-110">この例では、`AddHandler` アクセサーは、`Click` イベントの各ハンドラーのデリゲートを `EventHandlerList` フィールドに格納されている <xref:System.Collections.ArrayList> に追加します。</span><span class="sxs-lookup"><span data-stu-id="77660-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="77660-111">コードで `Click` イベントが発生すると、`RaiseEvent` アクセサーは <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> メソッドを使用して、すべてのイベントハンドラーデリゲートを非同期的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="77660-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="77660-112">このメソッドは、ワーカースレッド上の各ハンドラーを呼び出し、すぐに制御を戻します。そのため、ハンドラーは互いにブロックできません。</span><span class="sxs-lookup"><span data-stu-id="77660-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="77660-113">参照</span><span class="sxs-lookup"><span data-stu-id="77660-113">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="77660-114">イベント</span><span class="sxs-lookup"><span data-stu-id="77660-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="77660-115">方法: カスタム イベントを宣言してメモリを節約する</span><span class="sxs-lookup"><span data-stu-id="77660-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
