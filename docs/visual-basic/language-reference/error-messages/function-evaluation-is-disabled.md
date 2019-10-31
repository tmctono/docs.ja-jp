---
title: 前の関数の評価がタイムアウトしたため、関数の評価は無効になりました。
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: d004c89b742944622ce45e6a2be8d96116252745
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197568"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="b54bb-102">前の関数の評価がタイムアウトしたため、関数の評価は無効になりました。</span><span class="sxs-lookup"><span data-stu-id="b54bb-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="b54bb-103">以前の関数の評価がタイムアウトしたため、関数の評価が無効になっています。関数の評価を再度有効にするには、ステップを再度実行するか、デバッグを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="b54bb-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="b54bb-104">Visual Studio デバッガーで、プロシージャ呼び出しが式に指定されていますが、別の評価がタイムアウトしています。</span><span class="sxs-lookup"><span data-stu-id="b54bb-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="b54bb-105">プロシージャ呼び出しでタイムアウトが発生する原因として、無限ループまたは*無限ループ*が考えられます。</span><span class="sxs-lookup"><span data-stu-id="b54bb-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="b54bb-106">詳細については、「」を参照して[ください。次のステートメント](../../../visual-basic/language-reference/statements/for-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b54bb-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="b54bb-107">無限ループの特殊なケースは*再帰*的です。</span><span class="sxs-lookup"><span data-stu-id="b54bb-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="b54bb-108">詳細については、「[再帰プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b54bb-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="b54bb-109">**エラー ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="b54bb-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b54bb-110">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b54bb-110">To correct this error</span></span>  
  
1. <span data-ttu-id="b54bb-111">可能であれば、以前の関数の評価がどのようなものか、およびそれがタイムアウトになった原因を特定します。それ以外の場合は、このエラーが再度発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b54bb-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="b54bb-112">デバッガーのステップをもう一度実行するか、デバッガーを終了させて再起動します。</span><span class="sxs-lookup"><span data-stu-id="b54bb-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54bb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b54bb-113">See also</span></span>

- [<span data-ttu-id="b54bb-114">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="b54bb-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="b54bb-115">デバッガーでのコード間の移動</span><span class="sxs-lookup"><span data-stu-id="b54bb-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
