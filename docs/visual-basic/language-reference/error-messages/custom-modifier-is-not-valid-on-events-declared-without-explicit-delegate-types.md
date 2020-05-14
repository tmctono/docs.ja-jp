---
title: "'Custom' 修飾子は、明示的なデリゲート型なしで宣言されたイベントでは無効です。"
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 169cb49cc5abc76b7c52785392d0083b81a99450
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803884"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="c8bee-102">'Custom' 修飾子は、明示的なデリゲート型なしで宣言されたイベントでは無効です。</span><span class="sxs-lookup"><span data-stu-id="c8bee-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="c8bee-103">非カスタム イベントと異なり、`Custom Event` 宣言では、イベント名の後に、イベントのデリゲート型を明示的に指定する `As` 句が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8bee-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="c8bee-104">非カスタム イベントを定義するには、`As` 句と明示的なデリゲート型を使用するか、またはイベント名の直後にパラメーター リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8bee-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="c8bee-105">**エラー ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="c8bee-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c8bee-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c8bee-106">To correct this error</span></span>  
  
1. <span data-ttu-id="c8bee-107">カスタム イベントと同じパラメーター リストでデリゲートを定義します。</span><span class="sxs-lookup"><span data-stu-id="c8bee-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="c8bee-108">たとえば、`Custom Event` が `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` によって定義されている場合、対応するデリゲートは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c8bee-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="c8bee-109">カスタム イベントのパラメーター リストを、デリゲート型を指定する `As` 句に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c8bee-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="c8bee-110">この例を続行すると、`Custom Event` 宣言は次のように書き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c8bee-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="c8bee-111">例</span><span class="sxs-lookup"><span data-stu-id="c8bee-111">Example</span></span>  
 <span data-ttu-id="c8bee-112">この例では、`Custom Event` を宣言し、デリゲート型で必要な `As` 句を指定しています。</span><span class="sxs-lookup"><span data-stu-id="c8bee-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c8bee-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8bee-113">See also</span></span>

- [<span data-ttu-id="c8bee-114">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="c8bee-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="c8bee-115">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="c8bee-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="c8bee-116">イベント</span><span class="sxs-lookup"><span data-stu-id="c8bee-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
