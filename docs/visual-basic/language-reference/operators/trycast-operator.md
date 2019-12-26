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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348208"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="f3283-102">TryCast 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3283-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="f3283-103">例外をスローしない型変換操作を導入します。</span><span class="sxs-lookup"><span data-stu-id="f3283-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3283-104">コメント</span><span class="sxs-lookup"><span data-stu-id="f3283-104">Remarks</span></span>  
 <span data-ttu-id="f3283-105">変換の試行が失敗した場合、`CType` と `DirectCast` の両方で <xref:System.InvalidCastException> エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="f3283-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="f3283-106">これにより、アプリケーションのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3283-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="f3283-107">`TryCast` は [Nothing](../../../visual-basic/language-reference/nothing.md) を返します。そのため、考えられる例外を処理する代わりに、返された結果を `Nothing`に対してのみテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3283-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="f3283-108">`TryCast` キーワードは、[CType 関数](../../../visual-basic/language-reference/functions/ctype-function.md)と [DirectCast 演算子](../../../visual-basic/language-reference/operators/directcast-operator.md)キーワードを使用するのと同じ方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="f3283-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="f3283-109">最初の引数として式を指定し、2 番目の引数として変換する型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3283-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="f3283-110">`TryCast` は、クラスやインターフェイスなどの参照型に対してのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="f3283-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="f3283-111">2 つの型の間の継承または実装関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="f3283-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="f3283-112">これは、一方の型が他の型を継承または実装する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f3283-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="f3283-113">エラーとエラー</span><span class="sxs-lookup"><span data-stu-id="f3283-113">Errors and Failures</span></span>  
 <span data-ttu-id="f3283-114">`TryCast` は、継承または実装関係が存在しないことを検出すると、コンパイラエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="f3283-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="f3283-115">ただし、コンパイラエラーがないからといって、正常に変換できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="f3283-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="f3283-116">目的の変換が縮小されている場合は、実行時に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3283-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="f3283-117">この場合、`TryCast` は [Nothing](../../../visual-basic/language-reference/nothing.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="f3283-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="f3283-118">変換キーワード</span><span class="sxs-lookup"><span data-stu-id="f3283-118">Conversion Keywords</span></span>  
 <span data-ttu-id="f3283-119">型変換のキーワードの比較を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3283-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="f3283-120">Keyword</span><span class="sxs-lookup"><span data-stu-id="f3283-120">Keyword</span></span>|<span data-ttu-id="f3283-121">データの種類</span><span class="sxs-lookup"><span data-stu-id="f3283-121">Data types</span></span>|<span data-ttu-id="f3283-122">引数のリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="f3283-122">Argument relationship</span></span>|<span data-ttu-id="f3283-123">実行時エラー</span><span class="sxs-lookup"><span data-stu-id="f3283-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="f3283-124">CType 関数</span><span class="sxs-lookup"><span data-stu-id="f3283-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="f3283-125">任意のデータ型</span><span class="sxs-lookup"><span data-stu-id="f3283-125">Any data types</span></span>|<span data-ttu-id="f3283-126">拡大または縮小変換は、2 つのデータ型の間で定義する必要があります</span><span class="sxs-lookup"><span data-stu-id="f3283-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="f3283-127"><xref:System.InvalidCastException> をスロー</span><span class="sxs-lookup"><span data-stu-id="f3283-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="f3283-128">DirectCast 演算子</span><span class="sxs-lookup"><span data-stu-id="f3283-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="f3283-129">任意のデータ型</span><span class="sxs-lookup"><span data-stu-id="f3283-129">Any data types</span></span>|<span data-ttu-id="f3283-130">一方の型は、他の型を継承するか、他の型を実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="f3283-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="f3283-131"><xref:System.InvalidCastException> をスロー</span><span class="sxs-lookup"><span data-stu-id="f3283-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="f3283-132">参照型のみ</span><span class="sxs-lookup"><span data-stu-id="f3283-132">Reference types only</span></span>|<span data-ttu-id="f3283-133">一方の型は、他の型を継承するか、他の型を実装する必要があります</span><span class="sxs-lookup"><span data-stu-id="f3283-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="f3283-134">[Nothing](../../../visual-basic/language-reference/nothing.md) を返す</span><span class="sxs-lookup"><span data-stu-id="f3283-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f3283-135">例</span><span class="sxs-lookup"><span data-stu-id="f3283-135">Example</span></span>  
 <span data-ttu-id="f3283-136">次の例は、`TryCast` を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f3283-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="f3283-137">参照</span><span class="sxs-lookup"><span data-stu-id="f3283-137">See also</span></span>

- [<span data-ttu-id="f3283-138">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="f3283-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="f3283-139">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="f3283-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
