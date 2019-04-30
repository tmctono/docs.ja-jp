---
title: '方法: (Visual Basic) のメモリを節約するためにカスタム イベントを宣言します。'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: e4132f51f4dd85ad964042d05f7c5bc0a2e6e3cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973161"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="4fa9d-102">方法: (Visual Basic) のメモリを節約するためにカスタム イベントを宣言します。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="4fa9d-103">いくつかの状況があること、アプリケーションのメモリ使用量を低く抑える必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="4fa9d-104">カスタム イベントは、処理するイベントに対してだけメモリを使用するアプリケーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="4fa9d-105">既定では、クラスのイベントを宣言して、コンパイラは、イベント情報を格納するフィールドのメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="4fa9d-106">クラスに使用されていない多数のイベントがある場合は、不必要が必要になるメモリ。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="4fa9d-107">Visual Basic ではイベントの既定の実装を使用する代わりには、カスタム イベントを使用して、メモリ使用量をより慎重に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fa9d-108">例</span><span class="sxs-lookup"><span data-stu-id="4fa9d-108">Example</span></span>  
 <span data-ttu-id="4fa9d-109">この例で、クラスが 1 つのインスタンスを使用して、<xref:System.ComponentModel.EventHandlerList>に格納されているクラス、`Events`使用イベントについての情報を格納するためのフィールド。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="4fa9d-110"><xref:System.ComponentModel.EventHandlerList>クラスは、最適化されたリスト クラスのデリゲートを保持するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="4fa9d-111">クラスの使用中のすべてのイベント、`Events`どのような方法には、各イベントが処理を追跡するフィールド。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="4fa9d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fa9d-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="4fa9d-113">イベント</span><span class="sxs-lookup"><span data-stu-id="4fa9d-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="4fa9d-114">方法: ブロックを回避するためにカスタム イベントを宣言します。</span><span class="sxs-lookup"><span data-stu-id="4fa9d-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
