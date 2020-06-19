---
title: OrElse 演算子
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 3095a11523eeb8ec531c7f312fca74d2a070c92f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401408"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="68ba6-102">OrElse 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68ba6-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="68ba6-103">2 つの式の短絡包含的論理和を求めます。</span><span class="sxs-lookup"><span data-stu-id="68ba6-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ba6-104">構文</span><span class="sxs-lookup"><span data-stu-id="68ba6-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="68ba6-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="68ba6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="68ba6-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="68ba6-106">Required.</span></span> <span data-ttu-id="68ba6-107">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="68ba6-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="68ba6-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="68ba6-108">Required.</span></span> <span data-ttu-id="68ba6-109">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="68ba6-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="68ba6-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="68ba6-110">Required.</span></span> <span data-ttu-id="68ba6-111">任意のブール型 ( `Boolean` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="68ba6-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68ba6-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="68ba6-112">Remarks</span></span>  
 <span data-ttu-id="68ba6-113">コンパイルされたコードが、ある式の評価を別の式の結果に応じてバイパスできる場合、論理演算は "*短絡*" であると言われます。</span><span class="sxs-lookup"><span data-stu-id="68ba6-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="68ba6-114">最初に評価された式の結果によって演算の最終結果が決まる場合、最終結果を変更できないため、2 番目の式を評価する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="68ba6-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="68ba6-115">バイパスされた式が複雑な場合や、プロシージャ呼び出しが関係している場合に、短絡によってパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="68ba6-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="68ba6-116">いずれかまたは両方の式が `True` に評価される場合、`result` は `True` です。</span><span class="sxs-lookup"><span data-stu-id="68ba6-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="68ba6-117">次の表は、`result` がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="68ba6-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="68ba6-118">`expression1` が次の場合</span><span class="sxs-lookup"><span data-stu-id="68ba6-118">If `expression1` is</span></span>|<span data-ttu-id="68ba6-119">かつ、`expression2` が次の場合</span><span class="sxs-lookup"><span data-stu-id="68ba6-119">And `expression2` is</span></span>|<span data-ttu-id="68ba6-120">`result` の値は次のとおり</span><span class="sxs-lookup"><span data-stu-id="68ba6-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="68ba6-121">(評価されていない)</span><span class="sxs-lookup"><span data-stu-id="68ba6-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="68ba6-122">データの種類</span><span class="sxs-lookup"><span data-stu-id="68ba6-122">Data Types</span></span>  
 <span data-ttu-id="68ba6-123">`OrElse` 演算子は [Boolean データ型](../data-types/boolean-data-type.md)に対してのみ定義されます。</span><span class="sxs-lookup"><span data-stu-id="68ba6-123">The `OrElse` operator is defined only for the [Boolean Data Type](../data-types/boolean-data-type.md).</span></span> <span data-ttu-id="68ba6-124">Visual Basic は、式を評価する前に、必要に応じて各オペランドを `Boolean` に変換します。</span><span class="sxs-lookup"><span data-stu-id="68ba6-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="68ba6-125">結果を数値型に代入すると、Visual Basic によって `Boolean` からその型への変換が行われ、`False` が `0` になり、`True` が `-1` になります。</span><span class="sxs-lookup"><span data-stu-id="68ba6-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="68ba6-126">詳細については、[ブール型変換](../data-types/boolean-data-type.md#type-conversions)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="68ba6-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="68ba6-127">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="68ba6-127">Overloading</span></span>  
 <span data-ttu-id="68ba6-128">[Or 演算子](or-operator.md)と [IsTrue 演算子](istrue-operator.md)は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、このクラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="68ba6-128">The [Or Operator](or-operator.md) and the [IsTrue Operator](istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="68ba6-129">`Or` と `IsTrue` の演算子をオーバーロードすると、`OrElse` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="68ba6-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="68ba6-130">コードで、`Or` と `IsTrue` をオーバーロードするクラスまたは構造体で `OrElse` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="68ba6-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="68ba6-131">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68ba6-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="68ba6-132">例</span><span class="sxs-lookup"><span data-stu-id="68ba6-132">Example</span></span>  
 <span data-ttu-id="68ba6-133">次の例では、`OrElse` 演算子を使用して、2 つの式の論理和を求めます。</span><span class="sxs-lookup"><span data-stu-id="68ba6-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="68ba6-134">結果は、2 つの式のいずれかが true かどうかを表す `Boolean` 値です。</span><span class="sxs-lookup"><span data-stu-id="68ba6-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="68ba6-135">最初の式が `True` 場合、2 番目の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="68ba6-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="68ba6-136">前の例では、それぞれ `True`、`True`、`False` の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="68ba6-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="68ba6-137">`firstCheck` の計算では、最初の式が既に `True` であるため、2 番目の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="68ba6-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="68ba6-138">ただし、2 番目の式は `secondCheck` の計算で評価されます。</span><span class="sxs-lookup"><span data-stu-id="68ba6-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68ba6-139">例</span><span class="sxs-lookup"><span data-stu-id="68ba6-139">Example</span></span>  
 <span data-ttu-id="68ba6-140">次の例は、2 つのプロシージャ呼び出しを含む `If`...`Then` ステートメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="68ba6-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="68ba6-141">最初の呼び出しで `True` が返された場合、2 番目のプロシージャは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="68ba6-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="68ba6-142">コードのこのセクションの実行時に常に実行する必要がある重要なタスクを 2 番目のプロシージャが実行すると場合、予期しない結果が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68ba6-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="68ba6-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="68ba6-143">See also</span></span>

- [<span data-ttu-id="68ba6-144">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68ba6-144">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="68ba6-145">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="68ba6-145">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="68ba6-146">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="68ba6-146">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="68ba6-147">Or 演算子</span><span class="sxs-lookup"><span data-stu-id="68ba6-147">Or Operator</span></span>](or-operator.md)
- [<span data-ttu-id="68ba6-148">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="68ba6-148">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="68ba6-149">Visual Basic の論理演算子とビット演算子</span><span class="sxs-lookup"><span data-stu-id="68ba6-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
