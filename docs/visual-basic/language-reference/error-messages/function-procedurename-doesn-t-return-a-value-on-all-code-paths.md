---
title: 関数 '<procedurename>' すべてのコード パス上では値を返しません。
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 5564f95048f6b44a48229c7e5be9331839803439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662100"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="72538-102">関数 '\<procedurename >' は、すべてのコード パスで値を返しません</span><span class="sxs-lookup"><span data-stu-id="72538-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="72538-103">関数 '\<procedurename >' は、すべてのコード パスで値を返しません。</span><span class="sxs-lookup"><span data-stu-id="72538-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="72538-104">'Return' ステートメントが見当たりませんか。</span><span class="sxs-lookup"><span data-stu-id="72538-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="72538-105">A`Function`手順では、値を返さないコードの少なくとも 1 つの可能なパス。</span><span class="sxs-lookup"><span data-stu-id="72538-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="72538-106">値を返すことができます、`Function`次の方法のいずれかの手順。</span><span class="sxs-lookup"><span data-stu-id="72538-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="72538-107">値を含める、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="72538-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
- <span data-ttu-id="72538-108">値を代入します、`Function`プロシージャ名前を指定し、実行、`Exit Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="72538-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
- <span data-ttu-id="72538-109">値を代入します、`Function`プロシージャ名前を指定し、実行、`End Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="72538-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="72538-110">制御が`Exit Function`または`End Function`に渡り、プロシージャ名に任意の値が割り当てられていないと、戻り値のデータ型の既定値を返します。</span><span class="sxs-lookup"><span data-stu-id="72538-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="72538-111">詳細については、[Function ステートメント](../../../visual-basic/language-reference/statements/function-statement.md) の「動作」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72538-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="72538-112">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="72538-112">By default, this message is a warning.</span></span> <span data-ttu-id="72538-113">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72538-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="72538-114">**エラー ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="72538-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72538-115">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="72538-115">To correct this error</span></span>  
  
- <span data-ttu-id="72538-116">制御フローのロジックを確認し、すべてが値を返すステートメントの前に値を代入するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="72538-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="72538-117">常に使用する場合に、プロシージャからリターンごとに値を返すことを保証する方が簡単、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="72538-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="72538-118">この場合、最後のステートメントの前に`End Function`する必要があります、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="72538-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72538-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="72538-119">See also</span></span>

- [<span data-ttu-id="72538-120">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="72538-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="72538-121">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="72538-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- <span data-ttu-id="72538-122">[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="72538-122">[Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
