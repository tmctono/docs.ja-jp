---
title: DirectCast 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 628ce4f06b91d0f514f71dea3aad8ea0fee6dccf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778548"
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="dd515-102">DirectCast 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd515-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="dd515-103">継承または実装に基づいて、型変換操作をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dd515-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd515-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="dd515-104">Remarks</span></span>  
 <span data-ttu-id="dd515-105">`DirectCast` 変換で多少を提供できるように、ランタイム ヘルパー ルーチンに比べてパフォーマンスが向上する Visual Basic を使用しません`CType`との間のデータ型を変換するときに`Object`します。</span><span class="sxs-lookup"><span data-stu-id="dd515-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="dd515-106">使用する、`DirectCast`キーワードを使用するのと同様、 [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)と[TryCast 演算子](../../../visual-basic/language-reference/operators/trycast-operator.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="dd515-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="dd515-107">最初の引数と 2 番目の引数は変換する型として式を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd515-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="dd515-108">`DirectCast` 2 つの引数のデータ型の間の継承または実装のリレーションシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd515-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="dd515-109">つまり 1 つの型が継承または他の実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd515-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="dd515-110">エラーと障害</span><span class="sxs-lookup"><span data-stu-id="dd515-110">Errors and Failures</span></span>  
 <span data-ttu-id="dd515-111">`DirectCast` 継承または実装のリレーションシップが存在しないことが検出された場合は、コンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="dd515-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="dd515-112">コンパイラ エラーがないことに成功した変換が保証されません。</span><span class="sxs-lookup"><span data-stu-id="dd515-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="dd515-113">必要な変換を縮小すると、実行時に失敗する可能性が。</span><span class="sxs-lookup"><span data-stu-id="dd515-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="dd515-114">この場合、ランタイム、<xref:System.InvalidCastException>エラー。</span><span class="sxs-lookup"><span data-stu-id="dd515-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="dd515-115">変換キーワード</span><span class="sxs-lookup"><span data-stu-id="dd515-115">Conversion Keywords</span></span>  
 <span data-ttu-id="dd515-116">型変換のキーワードの比較は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dd515-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="dd515-117">キーワード</span><span class="sxs-lookup"><span data-stu-id="dd515-117">Keyword</span></span>|<span data-ttu-id="dd515-118">データの種類</span><span class="sxs-lookup"><span data-stu-id="dd515-118">Data types</span></span>|<span data-ttu-id="dd515-119">引数の関係</span><span class="sxs-lookup"><span data-stu-id="dd515-119">Argument relationship</span></span>|<span data-ttu-id="dd515-120">実行時エラー</span><span class="sxs-lookup"><span data-stu-id="dd515-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="dd515-121">CType 関数</span><span class="sxs-lookup"><span data-stu-id="dd515-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="dd515-122">すべてのデータ型</span><span class="sxs-lookup"><span data-stu-id="dd515-122">Any data types</span></span>|<span data-ttu-id="dd515-123">2 つのデータ型の間で拡大または縮小変換を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd515-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="dd515-124">スローされます。 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="dd515-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="dd515-125">すべてのデータ型</span><span class="sxs-lookup"><span data-stu-id="dd515-125">Any data types</span></span>|<span data-ttu-id="dd515-126">1 つの型を継承またはその他の型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd515-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="dd515-127">スローされます。 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="dd515-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="dd515-128">TryCast 演算子</span><span class="sxs-lookup"><span data-stu-id="dd515-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="dd515-129">参照型のみ</span><span class="sxs-lookup"><span data-stu-id="dd515-129">Reference types only</span></span>|<span data-ttu-id="dd515-130">1 つの型を継承またはその他の型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd515-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="dd515-131">返します[Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="dd515-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd515-132">例</span><span class="sxs-lookup"><span data-stu-id="dd515-132">Example</span></span>  
 <span data-ttu-id="dd515-133">次の例では、2 つの用途の`DirectCast`、いずれかのいずれかの実行時に失敗するが成功するとします。</span><span class="sxs-lookup"><span data-stu-id="dd515-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 <span data-ttu-id="dd515-134">前の例では、実行時の入力の`q`は`Double`します。</span><span class="sxs-lookup"><span data-stu-id="dd515-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="dd515-135">`CType` 成功`Double`に変換できる`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="dd515-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="dd515-136">ただし、最初の`DirectCast`実行時の型であるために、実行時に失敗`Double`継承関係を持たない`Integer`変換が存在する場合でも、します。</span><span class="sxs-lookup"><span data-stu-id="dd515-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="dd515-137">2 番目の`DirectCast`型からに変換されるためが成功すると<xref:System.Windows.Forms.Form>を入力する<xref:System.Windows.Forms.Control>、元の<xref:System.Windows.Forms.Form>継承します。</span><span class="sxs-lookup"><span data-stu-id="dd515-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd515-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd515-138">See also</span></span>

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="dd515-139">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="dd515-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="dd515-140">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="dd515-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
