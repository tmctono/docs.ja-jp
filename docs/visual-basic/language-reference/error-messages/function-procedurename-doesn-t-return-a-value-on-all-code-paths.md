---
title: 関数 '<procedurename>' すべてのコード パス上では値を返しません。
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: edb2195f4e83c2315aa929936aff8af88ca8556c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374136"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="13cd1-102">関数 '\<procedurename>' すべてのコード パス上では値を返しません。</span><span class="sxs-lookup"><span data-stu-id="13cd1-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="13cd1-103">関数 '\<procedurename>' がすべてのコード パス上では値を返しません。</span><span class="sxs-lookup"><span data-stu-id="13cd1-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="13cd1-104">'return' ステートメントが不足していませんか。</span><span class="sxs-lookup"><span data-stu-id="13cd1-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="13cd1-105">`Function` プロシージャに、値を返さないコードのパスが少なくとも 1 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="13cd1-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="13cd1-106">次のいずれかの方法で、`Function` プロシージャから値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="13cd1-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="13cd1-107">[return ステートメント](../statements/return-statement.md)に値を含めます。</span><span class="sxs-lookup"><span data-stu-id="13cd1-107">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>  
  
- <span data-ttu-id="13cd1-108">`Function` プロシージャ名に値を代入して、`Exit Function` ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="13cd1-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
- <span data-ttu-id="13cd1-109">`Function` プロシージャ名に値を代入して、`End Function` ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="13cd1-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="13cd1-110">制御が `Exit Function` または `End Function` に渡され、プロシージャ名に何も値を代入していない場合、プロシージャでは、戻り値のデータ型の既定値が返されます。</span><span class="sxs-lookup"><span data-stu-id="13cd1-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="13cd1-111">詳細については、「[Function ステートメント](../statements/function-statement.md)」の "動作" に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13cd1-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="13cd1-112">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="13cd1-112">By default, this message is a warning.</span></span> <span data-ttu-id="13cd1-113">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13cd1-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="13cd1-114">**エラー ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="13cd1-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="13cd1-115">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="13cd1-115">To correct this error</span></span>  
  
- <span data-ttu-id="13cd1-116">制御フロー ロジックをチェックし、戻り値を返すすべてのステートメントの前に値を代入してください。</span><span class="sxs-lookup"><span data-stu-id="13cd1-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="13cd1-117">常に `Return` ステートメントを使用すれば、プロシージャからのすべての戻り値で、値が返されることを簡単に保証できます。</span><span class="sxs-lookup"><span data-stu-id="13cd1-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="13cd1-118">これを実行する場合、`End Function` の前の最後のステートメントは、`Return` ステートメントでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="13cd1-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cd1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="13cd1-119">See also</span></span>

- [<span data-ttu-id="13cd1-120">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="13cd1-120">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="13cd1-121">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="13cd1-121">Function Statement</span></span>](../statements/function-statement.md)
- <span data-ttu-id="13cd1-122">[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="13cd1-122">[Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
