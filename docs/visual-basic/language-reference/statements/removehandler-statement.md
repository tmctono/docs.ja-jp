---
title: RemoveHandler ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 177952acf362ccb36a36b5f09b11a1a93dbefa29
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333037"
---
# <a name="removehandler-statement"></a><span data-ttu-id="685b2-102">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="685b2-102">RemoveHandler Statement</span></span>
<span data-ttu-id="685b2-103">イベントとイベントハンドラーの間の関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="685b2-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685b2-104">構文</span><span class="sxs-lookup"><span data-stu-id="685b2-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="685b2-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="685b2-105">Parts</span></span>  
  
|<span data-ttu-id="685b2-106">用語</span><span class="sxs-lookup"><span data-stu-id="685b2-106">Term</span></span>|<span data-ttu-id="685b2-107">Definition</span><span class="sxs-lookup"><span data-stu-id="685b2-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="685b2-108">処理されるイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="685b2-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="685b2-109">イベントを現在処理しているプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="685b2-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="685b2-110">コメント</span><span class="sxs-lookup"><span data-stu-id="685b2-110">Remarks</span></span>  
 <span data-ttu-id="685b2-111">`AddHandler` および `RemoveHandler` ステートメントを使用すると、プログラムの実行中に、特定のイベントのイベント処理をいつでも開始および停止できます。</span><span class="sxs-lookup"><span data-stu-id="685b2-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="685b2-112">カスタムイベントの場合は、`RemoveHandler` ステートメントによって、イベントの `RemoveHandler` アクセサーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="685b2-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="685b2-113">カスタムイベントの詳細については、「 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685b2-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="685b2-114">例</span><span class="sxs-lookup"><span data-stu-id="685b2-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="685b2-115">参照</span><span class="sxs-lookup"><span data-stu-id="685b2-115">See also</span></span>

- [<span data-ttu-id="685b2-116">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="685b2-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- <span data-ttu-id="685b2-117">[!](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="685b2-117">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
- [<span data-ttu-id="685b2-118">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="685b2-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="685b2-119">イベント</span><span class="sxs-lookup"><span data-stu-id="685b2-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
