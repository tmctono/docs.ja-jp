---
title: DirectCast 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 96cb2082d59373deb34d6894270205b7c1045850
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371519"
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="67344-102">DirectCast 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67344-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="67344-103">継承または実装に基づく型変換操作を導入します。</span><span class="sxs-lookup"><span data-stu-id="67344-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67344-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="67344-104">Remarks</span></span>  
 <span data-ttu-id="67344-105">`DirectCast` では、変換に Visual Basic ランタイム ヘルパー ルーチンが使用されないため、データ型 `Object` 間で変換を行う場合、`CType` よりも多少パフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67344-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="67344-106">`DirectCast` キーワードは、[CType 関数](../functions/ctype-function.md)および [TryCast 演算子](trycast-operator.md)キーワードを使用するのと同じ方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="67344-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../functions/ctype-function.md) and the [TryCast Operator](trycast-operator.md) keyword.</span></span> <span data-ttu-id="67344-107">1 番目の引数として式を指定し、2 番目の引数としてその式を変換する先の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="67344-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="67344-108">`DirectCast` には、2 つの引数のデータ型間の継承または実装関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="67344-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="67344-109">つまり、一方の型が他方の型を継承または実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67344-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="67344-110">エラーと障害</span><span class="sxs-lookup"><span data-stu-id="67344-110">Errors and Failures</span></span>  
 <span data-ttu-id="67344-111">`DirectCast` で、継承関係または実装関係が存在しないことが検出されると、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="67344-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="67344-112">ただし、コンパイラ エラーが発生しない場合でも、変換が正常に行われるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="67344-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="67344-113">目的の変換が縮小変換の場合、実行時に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67344-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="67344-114">これが発生すると、ランタイムで <xref:System.InvalidCastException> エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="67344-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="67344-115">変換キーワード</span><span class="sxs-lookup"><span data-stu-id="67344-115">Conversion Keywords</span></span>  
 <span data-ttu-id="67344-116">型変換のキーワードの比較を次に示します。</span><span class="sxs-lookup"><span data-stu-id="67344-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="67344-117">キーワード</span><span class="sxs-lookup"><span data-stu-id="67344-117">Keyword</span></span>|<span data-ttu-id="67344-118">データの種類</span><span class="sxs-lookup"><span data-stu-id="67344-118">Data types</span></span>|<span data-ttu-id="67344-119">引数の関係</span><span class="sxs-lookup"><span data-stu-id="67344-119">Argument relationship</span></span>|<span data-ttu-id="67344-120">ランタイム エラー</span><span class="sxs-lookup"><span data-stu-id="67344-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="67344-121">CType 関数</span><span class="sxs-lookup"><span data-stu-id="67344-121">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="67344-122">任意のデータ型</span><span class="sxs-lookup"><span data-stu-id="67344-122">Any data types</span></span>|<span data-ttu-id="67344-123">2 つのデータ型の間で拡大変換または縮小変換を定義する必要があります</span><span class="sxs-lookup"><span data-stu-id="67344-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="67344-124"><xref:System.InvalidCastException> をスローする</span><span class="sxs-lookup"><span data-stu-id="67344-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="67344-125">任意のデータ型</span><span class="sxs-lookup"><span data-stu-id="67344-125">Any data types</span></span>|<span data-ttu-id="67344-126">一方の型が他方の型を継承または実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="67344-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="67344-127"><xref:System.InvalidCastException> をスローする</span><span class="sxs-lookup"><span data-stu-id="67344-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="67344-128">TryCast 演算子</span><span class="sxs-lookup"><span data-stu-id="67344-128">TryCast Operator</span></span>](trycast-operator.md)|<span data-ttu-id="67344-129">参照型のみ</span><span class="sxs-lookup"><span data-stu-id="67344-129">Reference types only</span></span>|<span data-ttu-id="67344-130">一方の型が他方の型を継承または実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="67344-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="67344-131">[Nothing](../nothing.md) が返されます</span><span class="sxs-lookup"><span data-stu-id="67344-131">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="67344-132">例</span><span class="sxs-lookup"><span data-stu-id="67344-132">Example</span></span>  
 <span data-ttu-id="67344-133">次の例は、`DirectCast` の 2 つの使用方法を示しています。1 つは実行時に失敗し、もう 1 つは成功します。</span><span class="sxs-lookup"><span data-stu-id="67344-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 <span data-ttu-id="67344-134">前の例では、`q` の実行時の型が `Double` です。</span><span class="sxs-lookup"><span data-stu-id="67344-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="67344-135">`Double` は `Integer` に変換できるため、`CType` は成功します。</span><span class="sxs-lookup"><span data-stu-id="67344-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="67344-136">ただし、`Double` の実行時の型には `Integer` との継承関係がないため、変換が存在する場合でも、実行時に最初の `DirectCast` は失敗します。</span><span class="sxs-lookup"><span data-stu-id="67344-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="67344-137">2 番目の `DirectCast` は、型 <xref:System.Windows.Forms.Form> から型 <xref:System.Windows.Forms.Control> に変換し、そこから <xref:System.Windows.Forms.Form> が継承されるため、成功します。</span><span class="sxs-lookup"><span data-stu-id="67344-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67344-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="67344-138">See also</span></span>

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="67344-139">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="67344-139">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="67344-140">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="67344-140">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
