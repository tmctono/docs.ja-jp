---
title: '方法: カスタム イベントを宣言してメモリを節約する'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3cc2d3ea57f1a8daf704c2c929baf3f2acf78c17
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345132"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="96af8-102">方法: カスタム イベントを宣言してメモリを節約する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96af8-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="96af8-103">アプリケーションでメモリ使用量を少なくすることが重要な状況がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="96af8-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="96af8-104">カスタムイベントを使用すると、アプリケーションが処理するイベントにのみメモリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="96af8-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="96af8-105">既定では、クラスがイベントを宣言すると、コンパイラは、イベント情報を格納するために、フィールドにメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="96af8-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="96af8-106">クラスに使用されているイベントの数が多い場合は、不必要にメモリを占有します。</span><span class="sxs-lookup"><span data-stu-id="96af8-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="96af8-107">Visual Basic が提供するイベントの既定の実装を使用する代わりに、カスタムイベントを使用してメモリ使用量をより慎重に管理できます。</span><span class="sxs-lookup"><span data-stu-id="96af8-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96af8-108">例</span><span class="sxs-lookup"><span data-stu-id="96af8-108">Example</span></span>  
 <span data-ttu-id="96af8-109">この例では、クラスは、`Events` フィールドに格納されている <xref:System.ComponentModel.EventHandlerList> クラスの1つのインスタンスを使用して、使用中のイベントに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="96af8-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="96af8-110"><xref:System.ComponentModel.EventHandlerList> クラスは、デリゲートを保持するように設計された最適化リストクラスです。</span><span class="sxs-lookup"><span data-stu-id="96af8-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="96af8-111">クラスのすべてのイベントでは、`Events` フィールドを使用して、各イベントを処理しているメソッドを追跡します。</span><span class="sxs-lookup"><span data-stu-id="96af8-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="96af8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="96af8-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="96af8-113">イベント</span><span class="sxs-lookup"><span data-stu-id="96af8-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="96af8-114">方法: カスタム イベントを宣言してブロックを回避する</span><span class="sxs-lookup"><span data-stu-id="96af8-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
