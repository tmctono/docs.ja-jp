---
title: 前の関数の評価がタイムアウトしたため、関数の評価は無効になりました。
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 7b0113e9c1018772da6dc180f7fc5beb0e922917
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402954"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="c1909-102">前の関数の評価がタイムアウトしたため、関数の評価は無効になりました。</span><span class="sxs-lookup"><span data-stu-id="c1909-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="c1909-103">前の関数の評価がタイムアウトしたため、関数の評価は無効になりました。関数の評価をもう一度有効にするには、もう一度ステップを実行するか、またはデバッグを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="c1909-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="c1909-104">Visual Studio デバッガーで、プロシージャ呼び出しが式に指定されていますが、別の評価がタイムアウトしています。</span><span class="sxs-lookup"><span data-stu-id="c1909-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="c1909-105">プロシージャ呼び出しがタイム アウトした原因には、*無限ループ*などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="c1909-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="c1909-106">詳細については、「[For...Next ステートメント](../statements/for-next-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1909-106">For more information, see [For...Next Statement](../statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="c1909-107">無限ループの特殊なケースが*再帰*です。</span><span class="sxs-lookup"><span data-stu-id="c1909-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="c1909-108">詳細については、「[再帰プロシージャ](../../programming-guide/language-features/procedures/recursive-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1909-108">For more information, see [Recursive Procedures](../../programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="c1909-109">**エラー ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="c1909-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1909-110">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c1909-110">To correct this error</span></span>  
  
1. <span data-ttu-id="c1909-111">可能であれば、前回の関数の評価がどれかを判断し、タイムアウトした理由を調べます。判断できない場合、このエラーが再度表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c1909-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="c1909-112">デバッガーのステップをもう一度実行するか、デバッガーを終了させて再起動します。</span><span class="sxs-lookup"><span data-stu-id="c1909-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1909-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1909-113">See also</span></span>

- [<span data-ttu-id="c1909-114">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="c1909-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="c1909-115">デバッガーでのコード間の移動</span><span class="sxs-lookup"><span data-stu-id="c1909-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
