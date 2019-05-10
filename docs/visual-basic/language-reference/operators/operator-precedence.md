---
title: Visual Basic における演算子の優先順位
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: 95505fd593881ff27418c69550952d072b4e3949
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628872"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="e1c8a-102">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="e1c8a-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="e1c8a-103">いくつかの操作は、式の中で発生した場合、各部分が評価されと呼ばれる事前に定義された順序で解決*演算子の優先順位*します。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="e1c8a-104">優先順位の規則</span><span class="sxs-lookup"><span data-stu-id="e1c8a-104">Precedence Rules</span></span>  
 <span data-ttu-id="e1c8a-105">式には、複数のカテゴリからの演算子が含まれている場合は、次の規則に従って評価されます。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
- <span data-ttu-id="e1c8a-106">算術演算および連結演算子の優先順位が次のセクションで説明されているが、比較、論理よりも大きい優先順位とビットごとの演算子。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
- <span data-ttu-id="e1c8a-107">すべての比較演算子は、優先順位が等しく、論理とビットごとの演算子よりも大きい優先順位が算術演算および連結演算子よりも優先順位の低いすべてがあります。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
- <span data-ttu-id="e1c8a-108">論理/ビット処理演算子の優先順位が次のセクションで説明しますが、算術演算子、文字列連結演算子、および比較演算子よりも優先順位の低い。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
- <span data-ttu-id="e1c8a-109">左から右に優先順位の等しい演算子が評価された式で表示される順序で。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="e1c8a-110">優先順位</span><span class="sxs-lookup"><span data-stu-id="e1c8a-110">Precedence Order</span></span>  
 <span data-ttu-id="e1c8a-111">演算子は、次の優先順位で評価されます。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="e1c8a-112">Await 演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-112">Await Operator</span></span>  
 <span data-ttu-id="e1c8a-113">Await </span><span class="sxs-lookup"><span data-stu-id="e1c8a-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="e1c8a-114">算術演算および連結演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="e1c8a-115">指数 (`^`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="e1c8a-116">単項 id と否定 (`+`、 `–`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="e1c8a-117">乗算と除算の浮動小数点 (`*`、 `/`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="e1c8a-118">整数除算 (`\`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="e1c8a-119">剰余演算 (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="e1c8a-120">加算と減算 (`+`、 `–`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="e1c8a-121">文字列の連結 (`&`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="e1c8a-122">算術ビット シフト (`<<`、 `>>`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="e1c8a-123">比較演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-123">Comparison Operators</span></span>  
 <span data-ttu-id="e1c8a-124">すべての比較演算子 (`=`、 `<>`、 `<`、 `<=`、 `>`、 `>=`、 `Is`、 `IsNot`、 `Like`、 `TypeOf`.`Is`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="e1c8a-125">論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="e1c8a-126">否定 (`Not`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="e1c8a-127">組み合わせて (`And`、 `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="e1c8a-128">包括的論理和 (`Or`、 `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="e1c8a-129">排他的論理和 (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="e1c8a-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="e1c8a-130">コメント</span><span class="sxs-lookup"><span data-stu-id="e1c8a-130">Comments</span></span>  
 <span data-ttu-id="e1c8a-131">`=`演算子はのみ、等値比較演算子、代入演算子ではありません。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="e1c8a-132">文字列連結演算子 (`&`)、算術演算子ではありませんが、算術演算子を使用してグループ化の優先順位。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="e1c8a-133">`Is`と`IsNot`演算子は、オブジェクト参照の比較演算子。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="e1c8a-134">2 つのオブジェクトの値を比較しないでください。これらは、2 つのオブジェクト変数が同じオブジェクト インスタンスを参照しているかどうか判断のみを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="e1c8a-135">結合規則</span><span class="sxs-lookup"><span data-stu-id="e1c8a-135">Associativity</span></span>  
 <span data-ttu-id="e1c8a-136">同じ優先順位の演算子は、乗算と除算、たとえば、式にまとめて表示されます。 が発生すると、左から右に、コンパイラは各操作を評価します。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="e1c8a-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="e1c8a-138">1 番目の式では、除算 96/8 (これは、結果は 12) し、除算 12/4 で、結果は 3 です。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="e1c8a-139">コンパイラの操作を評価するため`n1`左右からから、評価は、同じの順序が明示的に示されたとき`n2`します。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="e1c8a-140">両方`n1`と`n2`3 つの結果になります。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="e1c8a-141">これに対し、`n3`かっこは、コンパイラは 8 の評価を強制するために、48 の結果を持つ/4 最初。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="e1c8a-142">この動作により演算子があると言います。*結合規則が左*Visual Basic でします。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="e1c8a-143">優先順位と結合規則の上書き</span><span class="sxs-lookup"><span data-stu-id="e1c8a-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="e1c8a-144">かっこを使用して、他のユーザーの前に評価する式の一部を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="e1c8a-145">これには、優先順位の順序と左結合の両方をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="e1c8a-146">Visual Basic では、常に外部の前にかっこで囲まれた操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="e1c8a-147">一方、かっこ内で保持通常の優先順位と結合規則にかっこを使用する場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="e1c8a-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e1c8a-148">The following example illustrates this.</span></span>  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1c8a-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1c8a-149">See also</span></span>

- [<span data-ttu-id="e1c8a-150">= 演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="e1c8a-151">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="e1c8a-152">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="e1c8a-153">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="e1c8a-154">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="e1c8a-155">Await 演算子</span><span class="sxs-lookup"><span data-stu-id="e1c8a-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="e1c8a-156">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="e1c8a-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e1c8a-157">演算子および式</span><span class="sxs-lookup"><span data-stu-id="e1c8a-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
