---
title: スタック領域が不足しています。(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 29dbdf74808fc98bb856483c3fd8e3a09a72113b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318794"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="b037e-102">スタック領域が不足しています。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b037e-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="b037e-103">スタックは、実行しているプログラムの要求で動的に拡張し、縮小がメモリの作業領域です。</span><span class="sxs-lookup"><span data-stu-id="b037e-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="b037e-104">その制限を超えました。</span><span class="sxs-lookup"><span data-stu-id="b037e-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b037e-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b037e-105">To correct this error</span></span>  
  
1. <span data-ttu-id="b037e-106">プロシージャが深すぎます。 入れ子にしないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b037e-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="b037e-107">再帰プロシージャが正常に終了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b037e-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="b037e-108">ローカル変数では、複数領域がある必要がある場合は、モジュール レベルでいくつかの変数を宣言することをお試しください。</span><span class="sxs-lookup"><span data-stu-id="b037e-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="b037e-109">できますも変数を宣言するすべての手順で静的前に追加して、 `Property`、 `Sub`、または`Function`キーワード`Static`します。</span><span class="sxs-lookup"><span data-stu-id="b037e-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="b037e-110">使用することができます、`Static`プロシージャ内で個々 の静的変数を宣言するステートメント。</span><span class="sxs-lookup"><span data-stu-id="b037e-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="b037e-111">固定長文字列が可変長の文字列よりも多くのスタック領域を使用して、可変長の文字列として、固定長文字列の一部を再定義します。</span><span class="sxs-lookup"><span data-stu-id="b037e-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="b037e-112">スタック領域必要ありません、モジュール レベルで文字列を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="b037e-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="b037e-113">数を確認してください。 入れ子になった`DoEvents`関数を使用して呼び出し、、`Calls`スタック上でアクティブなプロシージャ ビュー ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b037e-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="b037e-114">スタックに既にイベント プロシージャを呼び出すイベントをトリガーすることによって、「イベントの連鎖」が発生しなかったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b037e-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="b037e-115">イベントに cascade は、終了していない再帰プロシージャ呼び出しに似ていますがわかりにくく、コード内の明示的な呼び出しではなく、Visual Basic での呼び出しが行われるため。</span><span class="sxs-lookup"><span data-stu-id="b037e-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="b037e-116">使用して、`Calls`スタック上でアクティブなプロシージャ ビュー ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b037e-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b037e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b037e-117">See also</span></span>

- <span data-ttu-id="b037e-118">[[メモリ] ウィンドウ](/visualstudio/debugger/memory-windows)</span><span class="sxs-lookup"><span data-stu-id="b037e-118">[Memory Windows](/visualstudio/debugger/memory-windows)</span></span>
