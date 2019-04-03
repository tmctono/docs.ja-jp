---
title: TryCast 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: c0eea4565d5040bb00743fc7864ac15b0fccdea9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831593"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="73994-102">TryCast 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73994-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="73994-103">例外をスローしない型変換操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="73994-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73994-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="73994-104">Remarks</span></span>  
 <span data-ttu-id="73994-105">変換が失敗した場合、`CType`と`DirectCast`スロー両方、<xref:System.InvalidCastException>エラー。</span><span class="sxs-lookup"><span data-stu-id="73994-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="73994-106">これは、アプリケーションのパフォーマンスに悪影響を与える。</span><span class="sxs-lookup"><span data-stu-id="73994-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="73994-107">`TryCast` 返します[Nothing](../../../visual-basic/language-reference/nothing.md)、可能性のある例外を処理するのではなく、に対して返された結果をテストする必要がありますのみように`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="73994-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="73994-108">使用する、`TryCast`キーワードを使用する場合と同様、 [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)と[DirectCast 演算子](../../../visual-basic/language-reference/operators/directcast-operator.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="73994-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="73994-109">最初の引数と 2 番目の引数は変換する型として式を指定します。</span><span class="sxs-lookup"><span data-stu-id="73994-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="73994-110">`TryCast` クラスやインターフェイスなど、参照型に対してのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="73994-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="73994-111">2 つの型の間の継承または実装のリレーションシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="73994-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="73994-112">つまり 1 つの型が継承または他の実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73994-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="73994-113">エラーと障害</span><span class="sxs-lookup"><span data-stu-id="73994-113">Errors and Failures</span></span>  
 <span data-ttu-id="73994-114">`TryCast` 継承または実装のリレーションシップが存在しないことが検出された場合は、コンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="73994-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="73994-115">コンパイラ エラーがないことに成功した変換が保証されません。</span><span class="sxs-lookup"><span data-stu-id="73994-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="73994-116">必要な変換を縮小すると、実行時に失敗する可能性が。</span><span class="sxs-lookup"><span data-stu-id="73994-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="73994-117">この場合、`TryCast`返します[Nothing](../../../visual-basic/language-reference/nothing.md)します。</span><span class="sxs-lookup"><span data-stu-id="73994-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="73994-118">変換キーワード</span><span class="sxs-lookup"><span data-stu-id="73994-118">Conversion Keywords</span></span>  
 <span data-ttu-id="73994-119">型変換のキーワードの比較は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73994-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="73994-120">キーワード</span><span class="sxs-lookup"><span data-stu-id="73994-120">Keyword</span></span>|<span data-ttu-id="73994-121">データの種類</span><span class="sxs-lookup"><span data-stu-id="73994-121">Data types</span></span>|<span data-ttu-id="73994-122">引数の関係</span><span class="sxs-lookup"><span data-stu-id="73994-122">Argument relationship</span></span>|<span data-ttu-id="73994-123">実行時エラー</span><span class="sxs-lookup"><span data-stu-id="73994-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="73994-124">CType 関数</span><span class="sxs-lookup"><span data-stu-id="73994-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="73994-125">すべてのデータ型</span><span class="sxs-lookup"><span data-stu-id="73994-125">Any data types</span></span>|<span data-ttu-id="73994-126">2 つのデータ型の間で拡大または縮小変換を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73994-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="73994-127">スローされます。 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="73994-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="73994-128">DirectCast 演算子</span><span class="sxs-lookup"><span data-stu-id="73994-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="73994-129">すべてのデータ型</span><span class="sxs-lookup"><span data-stu-id="73994-129">Any data types</span></span>|<span data-ttu-id="73994-130">1 つの型を継承またはその他の型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73994-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="73994-131">スローされます。 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="73994-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="73994-132">参照型のみ</span><span class="sxs-lookup"><span data-stu-id="73994-132">Reference types only</span></span>|<span data-ttu-id="73994-133">1 つの型を継承またはその他の型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73994-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="73994-134">返します[Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="73994-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73994-135">例</span><span class="sxs-lookup"><span data-stu-id="73994-135">Example</span></span>  
 <span data-ttu-id="73994-136">次の例は、`TryCast` を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="73994-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="73994-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="73994-137">See also</span></span>

- [<span data-ttu-id="73994-138">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="73994-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="73994-139">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="73994-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
