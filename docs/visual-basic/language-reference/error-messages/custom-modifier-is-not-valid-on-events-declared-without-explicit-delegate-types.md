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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803884"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="fc9d0-102">'Custom' 修飾子は、明示的なデリゲート型なしで宣言されたイベントでは無効です。</span><span class="sxs-lookup"><span data-stu-id="fc9d0-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="fc9d0-103">非カスタム イベントとは異なり、`Custom Event`宣言が必要です、`As`句は次のイベント名を明示的にイベントのデリゲート型を指定します。</span><span class="sxs-lookup"><span data-stu-id="fc9d0-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="fc9d0-104">非カスタム イベントは、いずれかで定義されている、`As`句と明示的なデリゲート型、またはすぐにパラメーターを持つリスト次のイベント名。</span><span class="sxs-lookup"><span data-stu-id="fc9d0-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="fc9d0-105">**エラー ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="fc9d0-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fc9d0-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="fc9d0-106">To correct this error</span></span>  
  
1. <span data-ttu-id="fc9d0-107">カスタム イベントと同じパラメーター リストを持つデリゲートを定義します。</span><span class="sxs-lookup"><span data-stu-id="fc9d0-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="fc9d0-108">たとえば場合、`Custom Event`で定義された`Custom Event Test(ByVal sender As Object, ByVal i As Integer)`、対応するデリゲートは、次になります。</span><span class="sxs-lookup"><span data-stu-id="fc9d0-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="fc9d0-109">カスタム イベントのパラメーターのリストを置き換える、`As`デリゲート型を指定する句。</span><span class="sxs-lookup"><span data-stu-id="fc9d0-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="fc9d0-110">先ほどの例では、`Custom Event`宣言を次のように書き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="fc9d0-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="fc9d0-111">例</span><span class="sxs-lookup"><span data-stu-id="fc9d0-111">Example</span></span>  
 <span data-ttu-id="fc9d0-112">この例で宣言、`Custom Event`し、必要なを指定します`As`デリゲート型を含む句。</span><span class="sxs-lookup"><span data-stu-id="fc9d0-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fc9d0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc9d0-113">See also</span></span>

- [<span data-ttu-id="fc9d0-114">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="fc9d0-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="fc9d0-115">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="fc9d0-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="fc9d0-116">イベント</span><span class="sxs-lookup"><span data-stu-id="fc9d0-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
