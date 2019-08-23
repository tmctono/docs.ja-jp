---
title: AddHandler ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: a9913cd682e52562422ba140e27187d37c592684
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928938"
---
# <a name="addhandler-statement"></a><span data-ttu-id="9e293-102">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="9e293-102">AddHandler Statement</span></span>
<span data-ttu-id="9e293-103">実行時にイベントをイベントハンドラーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9e293-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e293-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e293-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="9e293-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9e293-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="9e293-106">event</span><span class="sxs-lookup"><span data-stu-id="9e293-106">event</span></span>|<span data-ttu-id="9e293-107">処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="9e293-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="9e293-108">イベントを処理するプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="9e293-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="9e293-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e293-109">Remarks</span></span>  
 <span data-ttu-id="9e293-110">`AddHandler`ステートメントと`RemoveHandler`ステートメントを使うと、プログラムの実行中にいつでもイベント処理を開始および停止できます。</span><span class="sxs-lookup"><span data-stu-id="9e293-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="9e293-111">`eventhandler`プロシージャのシグネチャは、`event`イベントのシグネチャと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e293-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="9e293-112">`Handles` キーワードと `AddHandler` ステートメントはどちらも特定のプロシージャで特定のイベントを処理するように指定できますが、両者には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="9e293-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="9e293-113">`AddHandler` ステートメントは、実行時にプロシージャをイベントに接続します。</span><span class="sxs-lookup"><span data-stu-id="9e293-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="9e293-114">`Handles` キーワードは、プロシージャの定義時に特定のイベントを処理するよう指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="9e293-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="9e293-115">詳細については、「[ハンドル](../../../visual-basic/language-reference/statements/handles-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e293-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e293-116">カスタムイベントの場合、 `AddHandler`ステートメントは、イベントの`AddHandler`アクセサーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9e293-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="9e293-117">カスタムイベントの詳細については、「 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e293-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e293-118">例</span><span class="sxs-lookup"><span data-stu-id="9e293-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="9e293-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e293-119">See also</span></span>

- [<span data-ttu-id="9e293-120">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="9e293-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="9e293-121">Handles</span><span class="sxs-lookup"><span data-stu-id="9e293-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="9e293-122">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="9e293-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="9e293-123">イベント</span><span class="sxs-lookup"><span data-stu-id="9e293-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
