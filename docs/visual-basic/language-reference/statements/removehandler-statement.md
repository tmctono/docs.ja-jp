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
ms.openlocfilehash: 3a839a7d05d05066f6c0f774a683c8fc83c19643
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957720"
---
# <a name="removehandler-statement"></a><span data-ttu-id="d301c-102">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="d301c-102">RemoveHandler Statement</span></span>
<span data-ttu-id="d301c-103">イベントとイベントハンドラーの間の関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="d301c-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d301c-104">構文</span><span class="sxs-lookup"><span data-stu-id="d301c-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="d301c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="d301c-105">Parts</span></span>  
  
|<span data-ttu-id="d301c-106">用語</span><span class="sxs-lookup"><span data-stu-id="d301c-106">Term</span></span>|<span data-ttu-id="d301c-107">定義</span><span class="sxs-lookup"><span data-stu-id="d301c-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="d301c-108">処理されるイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="d301c-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="d301c-109">イベントを現在処理しているプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="d301c-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d301c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d301c-110">Remarks</span></span>  
 <span data-ttu-id="d301c-111">ステートメント`AddHandler` と`RemoveHandler`ステートメントを使用すると、プログラムの実行中に、特定のイベントのイベント処理をいつでも開始および停止できます。</span><span class="sxs-lookup"><span data-stu-id="d301c-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d301c-112">カスタムイベントの場合、 `RemoveHandler`ステートメントは、イベントの`RemoveHandler`アクセサーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d301c-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="d301c-113">カスタムイベントの詳細については、「 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d301c-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d301c-114">例</span><span class="sxs-lookup"><span data-stu-id="d301c-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="d301c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d301c-115">See also</span></span>

- [<span data-ttu-id="d301c-116">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="d301c-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="d301c-117">Handles</span><span class="sxs-lookup"><span data-stu-id="d301c-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="d301c-118">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="d301c-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="d301c-119">イベント</span><span class="sxs-lookup"><span data-stu-id="d301c-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
