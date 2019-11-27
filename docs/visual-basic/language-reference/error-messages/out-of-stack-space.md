---
title: スタック領域が不足しています。
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 9ae604a9727413f2705d42a4b68f5a50b7dd3feb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349185"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="f775d-102">スタック領域が不足しています。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f775d-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="f775d-103">スタックは、実行中のプログラムの要求に応じて動的に拡張および縮小されるメモリの作業領域です。</span><span class="sxs-lookup"><span data-stu-id="f775d-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="f775d-104">制限を超えました。</span><span class="sxs-lookup"><span data-stu-id="f775d-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f775d-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f775d-105">To correct this error</span></span>  
  
1. <span data-ttu-id="f775d-106">プロシージャの入れ子のレベルが深すぎないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f775d-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="f775d-107">再帰プロシージャが正常に終了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="f775d-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="f775d-108">ローカル変数で使用できるよりも多くのローカル変数空間が必要な場合は、モジュールレベルでいくつかの変数を宣言してみてください。</span><span class="sxs-lookup"><span data-stu-id="f775d-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="f775d-109">また、`Static`で `Property`、`Sub`、または `Function` キーワードを前に付けて、プロシージャ内のすべての変数を静的に宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="f775d-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="f775d-110">または、`Static` ステートメントを使用して、プロシージャ内で個々の静的変数を宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="f775d-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="f775d-111">固定長文字列は可変長文字列よりも多くのスタック領域を使用するため、固定長文字列の一部を可変長文字列として再定義します。</span><span class="sxs-lookup"><span data-stu-id="f775d-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="f775d-112">モジュールレベルで、スタック領域を必要としない文字列を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f775d-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="f775d-113">[`Calls`] ダイアログボックスを使用して、スタック上でアクティブになっているプロシージャを表示して、入れ子になった `DoEvents` 関数呼び出しの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="f775d-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="f775d-114">既にスタックにあるイベントプロシージャを呼び出すイベントをトリガーすることによって、"イベントの連鎖" が発生していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f775d-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="f775d-115">イベント連鎖は、終了していない再帰プロシージャ呼び出しに似ていますが、コード内の明示的な呼び出しではなく Visual Basic によって呼び出しが行われるため、あまり明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="f775d-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="f775d-116">[`Calls`] ダイアログボックスを使用すると、スタック上でアクティブになっているプロシージャを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f775d-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f775d-117">参照</span><span class="sxs-lookup"><span data-stu-id="f775d-117">See also</span></span>

- <span data-ttu-id="f775d-118">[[メモリ] ウィンドウ](/visualstudio/debugger/memory-windows)</span><span class="sxs-lookup"><span data-stu-id="f775d-118">[Memory Windows](/visualstudio/debugger/memory-windows)</span></span>
