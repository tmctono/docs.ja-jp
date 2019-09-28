---
title: '&amp;演算子 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: aaa7c1b9ab7f6c920180d97b55c3bdeb23f00e02
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592243"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="e3e50-102">&amp;演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3e50-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="e3e50-103">2つの式の文字列連結を生成します。</span><span class="sxs-lookup"><span data-stu-id="e3e50-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3e50-104">構文</span><span class="sxs-lookup"><span data-stu-id="e3e50-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="e3e50-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e3e50-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e3e50-106">必須。</span><span class="sxs-lookup"><span data-stu-id="e3e50-106">Required.</span></span> <span data-ttu-id="e3e50-107">@No__t 0 または `Object` の変数。</span><span class="sxs-lookup"><span data-stu-id="e3e50-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="e3e50-108">必須。</span><span class="sxs-lookup"><span data-stu-id="e3e50-108">Required.</span></span> <span data-ttu-id="e3e50-109">@No__t-0 に変換されたデータ型を持つ任意の式。</span><span class="sxs-lookup"><span data-stu-id="e3e50-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="e3e50-110">必須。</span><span class="sxs-lookup"><span data-stu-id="e3e50-110">Required.</span></span> <span data-ttu-id="e3e50-111">@No__t-0 に変換されたデータ型を持つ任意の式。</span><span class="sxs-lookup"><span data-stu-id="e3e50-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3e50-112">コメント</span><span class="sxs-lookup"><span data-stu-id="e3e50-112">Remarks</span></span>  
 <span data-ttu-id="e3e50-113">@No__t-0 または `expression2` のデータ型が @no__t ではなく、`String` に拡大変換される場合は、`String` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e3e50-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="e3e50-114">いずれかのデータ型が `String` に拡大されない場合、コンパイラはエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="e3e50-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="e3e50-115">@No__t-0 のデータ型は `String` です。</span><span class="sxs-lookup"><span data-stu-id="e3e50-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="e3e50-116">一方または両方の式が[Nothing](../../../visual-basic/language-reference/nothing.md)に評価されるか、値が <xref:System.DBNull.Value?displayProperty=nameWithType> の場合は、値が "" である文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="e3e50-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3e50-117">@No__t-0 演算子は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="e3e50-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e3e50-118">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e3e50-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e3e50-119">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e50-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3e50-120">アンパサンド (&) 文字は、変数を type `Long` として識別するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3e50-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="e3e50-121">詳細については、「[型文字](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e50-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3e50-122">例</span><span class="sxs-lookup"><span data-stu-id="e3e50-122">Example</span></span>  
 <span data-ttu-id="e3e50-123">この例では、`&` 演算子を使用して、文字列の連結を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="e3e50-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="e3e50-124">結果は、2つの文字列オペランドの連結を表す文字列値です。</span><span class="sxs-lookup"><span data-stu-id="e3e50-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e3e50-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3e50-125">See also</span></span>

- [<span data-ttu-id="e3e50-126">& = 演算子</span><span class="sxs-lookup"><span data-stu-id="e3e50-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="e3e50-127">連結演算子</span><span class="sxs-lookup"><span data-stu-id="e3e50-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="e3e50-128">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="e3e50-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e3e50-129">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="e3e50-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e3e50-130">Visual Basic での連結演算子</span><span class="sxs-lookup"><span data-stu-id="e3e50-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
