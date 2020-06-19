---
title: 演算子の効率のよい組み合わせ
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 3088072646278dac13e4d483cb4f99297eaad9ca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403473"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="ac283-102">演算子の効率のよい組み合わせ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac283-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="ac283-103">複合式にはさまざまな演算子を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ac283-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="ac283-104">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="ac283-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="ac283-105">前の例のいずれかのような複雑な式を作成するには、演算子の優先順位のルールを十分に理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac283-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="ac283-106">詳細については、「[Visual Basic における演算子の優先順位](../../../language-reference/operators/operator-precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac283-106">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="ac283-107">かっこで囲まれた式</span><span class="sxs-lookup"><span data-stu-id="ac283-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="ac283-108">多くの場合、演算子の優先順位によって決定される順序とは異なる順序で操作を進める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac283-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="ac283-109">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac283-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="ac283-110">前の例では、`z` を `y` で乗算し、その結果を `4` に加算しています。</span><span class="sxs-lookup"><span data-stu-id="ac283-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="ac283-111">ただし、結果を `z` で乗算する前に `y` と `4` を加算する場合は、かっこを使用して通常の演算子の優先順位をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="ac283-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="ac283-112">式をかっこで囲むことで、演算子の優先順位に関係なく、強制的にその式が最初に評価されます。</span><span class="sxs-lookup"><span data-stu-id="ac283-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="ac283-113">前の例で強制的に最初に加算を行うには、次の例のように記述し直します。</span><span class="sxs-lookup"><span data-stu-id="ac283-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="ac283-114">前の例では、`y` と `4` を加算し、その合計を `z` で乗算しています。</span><span class="sxs-lookup"><span data-stu-id="ac283-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="ac283-115">入れ子になったかっこで囲まれた式</span><span class="sxs-lookup"><span data-stu-id="ac283-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="ac283-116">式を複数のレベルのかっこで入れ子にして、優先順位をさらにオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac283-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="ac283-117">かっこ内で最も深く入れ子にされている式が最初に評価され、次に最も深く入れ子にされている式、次に最も深く入れ子にされていない式、最後にかっこの外側の式が評価されます。</span><span class="sxs-lookup"><span data-stu-id="ac283-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="ac283-118">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="ac283-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="ac283-119">前の例では、最初に `z + 2` が評価され、その後、かっこで囲まれたその他の式が評価されます。</span><span class="sxs-lookup"><span data-stu-id="ac283-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="ac283-120">通常、加算または乗算よりも高い優先順位を持つ指数演算は、この例では最後に評価されます。これは、他の式がかっこで囲まれているためです。</span><span class="sxs-lookup"><span data-stu-id="ac283-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac283-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac283-121">See also</span></span>

- [<span data-ttu-id="ac283-122">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="ac283-122">Arithmetic Operators in Visual Basic</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="ac283-123">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="ac283-123">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="ac283-124">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="ac283-124">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="ac283-125">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac283-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="ac283-126">ブール式</span><span class="sxs-lookup"><span data-stu-id="ac283-126">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="ac283-127">値の比較</span><span class="sxs-lookup"><span data-stu-id="ac283-127">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="ac283-128">方法: 数値を計算する</span><span class="sxs-lookup"><span data-stu-id="ac283-128">How to: Calculate Numeric Values</span></span>](how-to-calculate-numeric-values.md)
- [<span data-ttu-id="ac283-129">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="ac283-129">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
