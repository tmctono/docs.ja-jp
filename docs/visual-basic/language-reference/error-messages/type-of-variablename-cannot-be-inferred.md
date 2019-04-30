---
title: ループの境界とステップの句が同じ型に変換されないため、'<variablename>' の型を推論できません
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: e90e881546c12df2c8b19ff03a4d4c7304c4596c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052678"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="5a0af-102">型 '\<variablename >' ループの境界とステップの変数が同じ型に変換されないため、推論することはできません</span><span class="sxs-lookup"><span data-stu-id="5a0af-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="5a0af-103">記述した、`For...Next`をコンパイラを推論できませんループ コントロール変数のデータ型を次の条件に当てはまるため、ループ。</span><span class="sxs-lookup"><span data-stu-id="5a0af-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
- <span data-ttu-id="5a0af-104">ループ コントロール変数のデータ型が `As` 句で指定されていません。</span><span class="sxs-lookup"><span data-stu-id="5a0af-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
- <span data-ttu-id="5a0af-105">ループ境界とステップ変数に少なくとも 2 つのデータ型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a0af-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
- <span data-ttu-id="5a0af-106">データ型の間で変換する標準変換が存在しません。</span><span class="sxs-lookup"><span data-stu-id="5a0af-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="5a0af-107">そのため、コンパイラはループの制御変数のデータ型を推論できません。</span><span class="sxs-lookup"><span data-stu-id="5a0af-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="5a0af-108">次の例では、ステップの変数は文字であり、ループの境界はいずれも整数。</span><span class="sxs-lookup"><span data-stu-id="5a0af-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="5a0af-109">文字および整数間の標準変換がないため、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a0af-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="5a0af-110">**エラー ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="5a0af-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a0af-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5a0af-111">To correct this error</span></span>  
  
- <span data-ttu-id="5a0af-112">少なくとも 1 つに、他のユーザーに拡大変換する型は、ループの境界と必要に応じて、ステップの変数の型を変更します。</span><span class="sxs-lookup"><span data-stu-id="5a0af-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="5a0af-113">前の例では、変更の種類`stepVar`に`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="5a0af-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="5a0af-114">または</span><span class="sxs-lookup"><span data-stu-id="5a0af-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
- <span data-ttu-id="5a0af-115">ループの境界とステップの変数を適切な型に変換するのにには、明示的な変換関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a0af-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="5a0af-116">前の例では、適用、`Val`関数を`stepVar`します。</span><span class="sxs-lookup"><span data-stu-id="5a0af-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5a0af-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a0af-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="5a0af-118">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a0af-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="5a0af-119">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="5a0af-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="5a0af-120">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="5a0af-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="5a0af-121">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a0af-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="5a0af-122">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="5a0af-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5a0af-123">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="5a0af-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
