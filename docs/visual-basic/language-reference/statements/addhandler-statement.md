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
ms.openlocfilehash: 1e8d8f512f163d82f074a5ad53fbb38a10904dfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054303"
---
# <a name="addhandler-statement"></a><span data-ttu-id="24ffa-102">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="24ffa-102">AddHandler Statement</span></span>
<span data-ttu-id="24ffa-103">実行時にイベントをイベント ハンドラーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="24ffa-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ffa-104">構文</span><span class="sxs-lookup"><span data-stu-id="24ffa-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="24ffa-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="24ffa-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="24ffa-106">event</span><span class="sxs-lookup"><span data-stu-id="24ffa-106">event</span></span>|<span data-ttu-id="24ffa-107">処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="24ffa-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="24ffa-108">イベントを処理するプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="24ffa-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="24ffa-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="24ffa-109">Remarks</span></span>  
 <span data-ttu-id="24ffa-110">`AddHandler`ステートメントと`RemoveHandler`ステートメントを使うと、プログラムの実行中にいつでもイベント処理を開始および停止できます。</span><span class="sxs-lookup"><span data-stu-id="24ffa-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="24ffa-111">`eventhandler`プロシージャのシグネチャは、`event`イベントのシグネチャと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24ffa-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="24ffa-112">`Handles` キーワードと `AddHandler` ステートメントはどちらも特定のプロシージャで特定のイベントを処理するように指定できますが、両者には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="24ffa-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="24ffa-113">`AddHandler` ステートメントは、実行時にプロシージャをイベントに接続します。</span><span class="sxs-lookup"><span data-stu-id="24ffa-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="24ffa-114">`Handles` キーワードは、プロシージャの定義時に特定のイベントを処理するよう指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="24ffa-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="24ffa-115">詳細については、次を参照してください。[処理](../../../visual-basic/language-reference/statements/handles-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="24ffa-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24ffa-116">カスタム イベントの場合、`AddHandler`ステートメントで呼び出されるイベントの`AddHandler`アクセサー。</span><span class="sxs-lookup"><span data-stu-id="24ffa-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="24ffa-117">カスタム イベントの詳細については、次を参照してください。 [Event ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="24ffa-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="24ffa-118">例</span><span class="sxs-lookup"><span data-stu-id="24ffa-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="24ffa-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="24ffa-119">See also</span></span>

- [<span data-ttu-id="24ffa-120">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="24ffa-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="24ffa-121">Handles</span><span class="sxs-lookup"><span data-stu-id="24ffa-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="24ffa-122">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="24ffa-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="24ffa-123">イベント</span><span class="sxs-lookup"><span data-stu-id="24ffa-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
