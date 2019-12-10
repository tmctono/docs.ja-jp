---
title: AddHandler ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350189"
---
# <a name="addhandler-statement"></a><span data-ttu-id="c65b1-102">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="c65b1-102">AddHandler Statement</span></span>
<span data-ttu-id="c65b1-103">実行時にイベントをイベントハンドラーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c65b1-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="c65b1-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="c65b1-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="c65b1-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="c65b1-106">イベント</span><span class="sxs-lookup"><span data-stu-id="c65b1-106">event</span></span>|<span data-ttu-id="c65b1-107">処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="c65b1-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="c65b1-108">イベントを処理するプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="c65b1-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="c65b1-109">コメント</span><span class="sxs-lookup"><span data-stu-id="c65b1-109">Remarks</span></span>  
 <span data-ttu-id="c65b1-110">`AddHandler` および `RemoveHandler` ステートメントを使用すると、プログラムの実行中にいつでもイベント処理を開始および停止できます。</span><span class="sxs-lookup"><span data-stu-id="c65b1-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="c65b1-111">`eventhandler` プロシージャのシグネチャは、イベント `event`の署名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65b1-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="c65b1-112">`Handles` キーワードと `AddHandler` ステートメントはどちらも特定のプロシージャで特定のイベントを処理するように指定できますが、両者には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="c65b1-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="c65b1-113">`AddHandler` ステートメントは、実行時にプロシージャをイベントに接続させます。</span><span class="sxs-lookup"><span data-stu-id="c65b1-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="c65b1-114">`Handles` キーワードは、プロシージャの定義時に特定のイベントを処理するよう指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="c65b1-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="c65b1-115">詳細については、「[Handles 句 (Visual Basic)](../../../visual-basic/language-reference/statements/handles-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65b1-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c65b1-116">カスタムイベントの場合は、`AddHandler` ステートメントによって、イベントの `AddHandler` アクセサーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c65b1-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="c65b1-117">カスタムイベントの詳細については、「[Event ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65b1-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c65b1-118">例</span><span class="sxs-lookup"><span data-stu-id="c65b1-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="c65b1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c65b1-119">See also</span></span>

- [<span data-ttu-id="c65b1-120">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="c65b1-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- <span data-ttu-id="c65b1-121">[!](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="c65b1-121">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
- [<span data-ttu-id="c65b1-122">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="c65b1-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="c65b1-123">イベント</span><span class="sxs-lookup"><span data-stu-id="c65b1-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
