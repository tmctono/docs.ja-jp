---
title: TryCast 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 53306575cfc385039be3939fd87cf993b4509af4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348208"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="53805-102">TryCast 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53805-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="53805-103">例外をスローしない型変換操作を導入します。</span><span class="sxs-lookup"><span data-stu-id="53805-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53805-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="53805-104">Remarks</span></span>  
 <span data-ttu-id="53805-105">試行された変換が失敗した場合、`CType` と `DirectCast` はどちらも <xref:System.InvalidCastException> エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="53805-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="53805-106">これは、アプリケーションのパフォーマンスに悪影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53805-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="53805-107">`TryCast` は [Nothing](../../../visual-basic/language-reference/nothing.md) を返します。そのため、発生する可能性がある例外を処理する必要はなく、代わりに、返された結果を `Nothing` に対してテストすることのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="53805-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="53805-108">`TryCast` キーワードは、[CType 関数](../../../visual-basic/language-reference/functions/ctype-function.md)および [DirectCast 演算子](../../../visual-basic/language-reference/operators/directcast-operator.md)キーワードを使用するのと同じ方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="53805-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="53805-109">1 番目の引数として式を指定し、2 番目の引数としてその式の変換先の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="53805-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="53805-110">`TryCast` は、クラスやインターフェイスなどの参照型に対してのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="53805-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="53805-111">2 つの型間の継承関係または実装関係が必要になります。</span><span class="sxs-lookup"><span data-stu-id="53805-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="53805-112">つまり、一方の型が他方の型を継承または実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53805-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="53805-113">エラーと障害</span><span class="sxs-lookup"><span data-stu-id="53805-113">Errors and Failures</span></span>  
 <span data-ttu-id="53805-114">`TryCast` で、継承関係または実装関係が存在しないことが検出されると、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="53805-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="53805-115">ただし、コンパイラ エラーが発生しない場合でも、変換が正常に行われるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="53805-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="53805-116">目的の変換が縮小変換の場合、実行時に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53805-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="53805-117">これが発生すると、`TryCast` は [Nothing](../../../visual-basic/language-reference/nothing.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="53805-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="53805-118">変換キーワード</span><span class="sxs-lookup"><span data-stu-id="53805-118">Conversion Keywords</span></span>  
 <span data-ttu-id="53805-119">型変換のキーワードの比較を次に示します。</span><span class="sxs-lookup"><span data-stu-id="53805-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="53805-120">キーワード</span><span class="sxs-lookup"><span data-stu-id="53805-120">Keyword</span></span>|<span data-ttu-id="53805-121">データの種類</span><span class="sxs-lookup"><span data-stu-id="53805-121">Data types</span></span>|<span data-ttu-id="53805-122">引数の関係</span><span class="sxs-lookup"><span data-stu-id="53805-122">Argument relationship</span></span>|<span data-ttu-id="53805-123">ランタイム エラー</span><span class="sxs-lookup"><span data-stu-id="53805-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="53805-124">CType 関数</span><span class="sxs-lookup"><span data-stu-id="53805-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="53805-125">任意のデータ型</span><span class="sxs-lookup"><span data-stu-id="53805-125">Any data types</span></span>|<span data-ttu-id="53805-126">2 つのデータ型の間で拡大変換または縮小変換を定義する必要があります</span><span class="sxs-lookup"><span data-stu-id="53805-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="53805-127"><xref:System.InvalidCastException> がスローされます</span><span class="sxs-lookup"><span data-stu-id="53805-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="53805-128">DirectCast 演算子</span><span class="sxs-lookup"><span data-stu-id="53805-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="53805-129">任意のデータ型</span><span class="sxs-lookup"><span data-stu-id="53805-129">Any data types</span></span>|<span data-ttu-id="53805-130">一方の型が他方の型を継承または実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="53805-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="53805-131"><xref:System.InvalidCastException> がスローされます</span><span class="sxs-lookup"><span data-stu-id="53805-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="53805-132">参照型のみ</span><span class="sxs-lookup"><span data-stu-id="53805-132">Reference types only</span></span>|<span data-ttu-id="53805-133">一方の型が他方の型を継承または実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="53805-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="53805-134">[Nothing](../../../visual-basic/language-reference/nothing.md) が返されます</span><span class="sxs-lookup"><span data-stu-id="53805-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="53805-135">例</span><span class="sxs-lookup"><span data-stu-id="53805-135">Example</span></span>  
 <span data-ttu-id="53805-136">次の例は、`TryCast` を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="53805-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="53805-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="53805-137">See also</span></span>

- [<span data-ttu-id="53805-138">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="53805-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="53805-139">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="53805-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
