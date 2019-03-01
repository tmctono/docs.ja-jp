---
title: RemoveHandler ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 4e53398f97cbd320c0c98250ac5abbc2e4e98027
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981037"
---
# <a name="removehandler-statement"></a><span data-ttu-id="77963-102">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="77963-102">RemoveHandler Statement</span></span>
<span data-ttu-id="77963-103">イベントとイベント ハンドラー間の関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="77963-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77963-104">構文</span><span class="sxs-lookup"><span data-stu-id="77963-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="77963-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="77963-105">Parts</span></span>  
  
|<span data-ttu-id="77963-106">用語</span><span class="sxs-lookup"><span data-stu-id="77963-106">Term</span></span>|<span data-ttu-id="77963-107">定義</span><span class="sxs-lookup"><span data-stu-id="77963-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="77963-108">処理されるイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="77963-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="77963-109">現在、イベントを処理するプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="77963-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77963-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="77963-110">Remarks</span></span>  
 <span data-ttu-id="77963-111">`AddHandler`と`RemoveHandler`ステートメントでは、開始およびプログラムの実行中にいつでも、特定のイベントのイベント処理を停止することができます。</span><span class="sxs-lookup"><span data-stu-id="77963-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77963-112">カスタム イベントの場合、`RemoveHandler`ステートメントで呼び出されるイベントの`RemoveHandler`アクセサー。</span><span class="sxs-lookup"><span data-stu-id="77963-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="77963-113">カスタム イベントの詳細については、次を参照してください。 [Event ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="77963-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77963-114">例</span><span class="sxs-lookup"><span data-stu-id="77963-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="77963-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="77963-115">See also</span></span>
- [<span data-ttu-id="77963-116">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="77963-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="77963-117">Handles</span><span class="sxs-lookup"><span data-stu-id="77963-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="77963-118">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="77963-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="77963-119">イベント</span><span class="sxs-lookup"><span data-stu-id="77963-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
