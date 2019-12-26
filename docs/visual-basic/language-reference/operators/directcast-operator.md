---
title: DirectCast 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 8ea29b80cf27bbb2c21a8cebbfaa0a294e05f11d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331314"
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="30644-102">DirectCast 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30644-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="30644-103">継承または実装に基づく型変換操作を導入します。</span><span class="sxs-lookup"><span data-stu-id="30644-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30644-104">コメント</span><span class="sxs-lookup"><span data-stu-id="30644-104">Remarks</span></span>  
 <span data-ttu-id="30644-105">`DirectCast` では、変換に Visual Basic ランタイムヘルパールーチンを使用しないため、データ型 `Object`との間で変換を行う場合は `CType` よりも多少優れたパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="30644-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="30644-106">[CType 関数](../../../visual-basic/language-reference/functions/ctype-function.md)および [TryCast 演算子](../../../visual-basic/language-reference/operators/trycast-operator.md)キーワードの使用方法と同様に、`DirectCast` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="30644-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="30644-107">最初の引数として式を指定し、2 番目の引数として変換する型を指定します。</span><span class="sxs-lookup"><span data-stu-id="30644-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="30644-108">`DirectCast` には、2 つの引数のデータ型間の継承または実装関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="30644-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="30644-109">これは、一方の型が他の型を継承または実装する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="30644-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="30644-110">エラーとエラー</span><span class="sxs-lookup"><span data-stu-id="30644-110">Errors and Failures</span></span>  
 <span data-ttu-id="30644-111">`DirectCast` は、継承または実装関係が存在しないことを検出すると、コンパイラエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="30644-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="30644-112">ただし、コンパイラエラーが発生しても、正常に変換できないことは保証されません。</span><span class="sxs-lookup"><span data-stu-id="30644-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="30644-113">目的の変換が縮小されている場合は、実行時に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30644-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="30644-114">これが発生すると、ランタイムは <xref:System.InvalidCastException> エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="30644-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="30644-115">変換キーワード</span><span class="sxs-lookup"><span data-stu-id="30644-115">Conversion Keywords</span></span>  
 <span data-ttu-id="30644-116">型変換のキーワードの比較を次に示します。</span><span class="sxs-lookup"><span data-stu-id="30644-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="30644-117">Keyword</span><span class="sxs-lookup"><span data-stu-id="30644-117">Keyword</span></span>|<span data-ttu-id="30644-118">データの種類</span><span class="sxs-lookup"><span data-stu-id="30644-118">Data types</span></span>|<span data-ttu-id="30644-119">引数のリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="30644-119">Argument relationship</span></span>|<span data-ttu-id="30644-120">実行時エラー</span><span class="sxs-lookup"><span data-stu-id="30644-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="30644-121">CType 関数</span><span class="sxs-lookup"><span data-stu-id="30644-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="30644-122">任意のデータ型</span><span class="sxs-lookup"><span data-stu-id="30644-122">Any data types</span></span>|<span data-ttu-id="30644-123">拡大または縮小変換は、2 つのデータ型の間で定義する必要があります</span><span class="sxs-lookup"><span data-stu-id="30644-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="30644-124"><xref:System.InvalidCastException> をスロー</span><span class="sxs-lookup"><span data-stu-id="30644-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="30644-125">任意のデータ型</span><span class="sxs-lookup"><span data-stu-id="30644-125">Any data types</span></span>|<span data-ttu-id="30644-126">一方の型は、他の型を継承するか、他の型を実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="30644-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="30644-127"><xref:System.InvalidCastException> をスロー</span><span class="sxs-lookup"><span data-stu-id="30644-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="30644-128">TryCast 演算子</span><span class="sxs-lookup"><span data-stu-id="30644-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="30644-129">参照型のみ</span><span class="sxs-lookup"><span data-stu-id="30644-129">Reference types only</span></span>|<span data-ttu-id="30644-130">一方の型は、他の型を継承するか、他の型を実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="30644-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="30644-131">[Nothing](../../../visual-basic/language-reference/nothing.md) を返す</span><span class="sxs-lookup"><span data-stu-id="30644-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="30644-132">例</span><span class="sxs-lookup"><span data-stu-id="30644-132">Example</span></span>  
 <span data-ttu-id="30644-133">次の例は、`DirectCast`の2つの使用方法を示しています。1つは実行時に失敗し、もう1つは成功します。</span><span class="sxs-lookup"><span data-stu-id="30644-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 <span data-ttu-id="30644-134">前の例では、`q` の実行時の型が `Double`になっています。</span><span class="sxs-lookup"><span data-stu-id="30644-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="30644-135">`Double` は `Integer`に変換できるため、`CType` は成功します。</span><span class="sxs-lookup"><span data-stu-id="30644-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="30644-136">ただし、変換が存在する場合でも、`Double` の実行時の型には `Integer`との継承関係がないため、実行時に最初の `DirectCast` は失敗します。</span><span class="sxs-lookup"><span data-stu-id="30644-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="30644-137">2番目の `DirectCast` は、<xref:System.Windows.Forms.Form> が継承する型 <xref:System.Windows.Forms.Form> から型 <xref:System.Windows.Forms.Control>に変換するため、成功します。</span><span class="sxs-lookup"><span data-stu-id="30644-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30644-138">参照</span><span class="sxs-lookup"><span data-stu-id="30644-138">See also</span></span>

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="30644-139">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="30644-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="30644-140">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="30644-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
