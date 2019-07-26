---
title: ループの境界とステップの句が同じ型に変換されないため、'<variablename>' の型を推論できません
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: c3086f79fb71693810bc8f14e8c0f493aa1e6515
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512704"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="37ec5-102">ループの境界\<とステップの変数が同じ型に拡大変換されないため、' variablename > ' の型を推論できません</span><span class="sxs-lookup"><span data-stu-id="37ec5-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="37ec5-103">次の条件が`For...Next`満たされているため、コンパイラが loop コントロール変数のデータ型を推論できないループが記述されました。</span><span class="sxs-lookup"><span data-stu-id="37ec5-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="37ec5-104">ループ コントロール変数のデータ型が `As` 句で指定されていません。</span><span class="sxs-lookup"><span data-stu-id="37ec5-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="37ec5-105">ループ境界とステップ変数に少なくとも 2 つのデータ型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="37ec5-105">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="37ec5-106">データ型の間に標準変換は存在しません。</span><span class="sxs-lookup"><span data-stu-id="37ec5-106">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="37ec5-107">そのため、コンパイラは、ループのコントロール変数のデータ型を推論できません。</span><span class="sxs-lookup"><span data-stu-id="37ec5-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="37ec5-108">次の例では、ステップ変数は文字で、ループの境界は両方とも整数です。</span><span class="sxs-lookup"><span data-stu-id="37ec5-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="37ec5-109">文字と整数の間に標準の変換がないため、このエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="37ec5-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="37ec5-110">**エラー ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="37ec5-110">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="37ec5-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="37ec5-111">To correct this error</span></span>

- <span data-ttu-id="37ec5-112">ループの境界とステップの変数の型を必要に応じて変更して、そのうち少なくとも1つが、他の型が拡大する型になるようにします。</span><span class="sxs-lookup"><span data-stu-id="37ec5-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="37ec5-113">前の例では、の`stepVar`型をに`Integer`変更します。</span><span class="sxs-lookup"><span data-stu-id="37ec5-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="37ec5-114">\- または -</span><span class="sxs-lookup"><span data-stu-id="37ec5-114">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="37ec5-115">明示的な変換関数を使用して、ループの境界とステップ変数を適切な型に変換します。</span><span class="sxs-lookup"><span data-stu-id="37ec5-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="37ec5-116">前の例では、 `Val`関数をに`stepVar`適用します。</span><span class="sxs-lookup"><span data-stu-id="37ec5-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="37ec5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="37ec5-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="37ec5-118">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="37ec5-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="37ec5-119">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="37ec5-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="37ec5-120">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="37ec5-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="37ec5-121">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="37ec5-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="37ec5-122">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="37ec5-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="37ec5-123">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="37ec5-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
