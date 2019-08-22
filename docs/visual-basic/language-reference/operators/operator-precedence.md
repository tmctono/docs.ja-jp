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
ms.openlocfilehash: df40aced45442c9c7895c8d10ece64b21e292508
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659924"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="2cf64-102">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="2cf64-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="2cf64-103">式の中で複数の操作が発生した場合、各部分は、演算子の*優先順位*と呼ばれる事前に定義された順序で評価および解決されます。</span><span class="sxs-lookup"><span data-stu-id="2cf64-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>

## <a name="precedence-rules"></a><span data-ttu-id="2cf64-104">優先順位の規則</span><span class="sxs-lookup"><span data-stu-id="2cf64-104">Precedence Rules</span></span>
 <span data-ttu-id="2cf64-105">式に複数のカテゴリの演算子が含まれている場合は、次の規則に従って評価されます。</span><span class="sxs-lookup"><span data-stu-id="2cf64-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>

- <span data-ttu-id="2cf64-106">算術演算子と連結演算子の優先順位は次のセクションで説明しています。また、すべての演算子は、比較演算子、論理演算子、ビットごとの演算子よりも優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="2cf64-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>

- <span data-ttu-id="2cf64-107">すべての比較演算子の優先順位は同じで、すべての比較演算子は論理演算子とビット処理演算子よりも優先順位が高くなりますが、算術演算子と連結演算子より優先順位は低くなります。</span><span class="sxs-lookup"><span data-stu-id="2cf64-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>

- <span data-ttu-id="2cf64-108">論理演算子とビット処理演算子は、次のセクションで説明する優先順位を持ち、算術演算子、連結演算子、および比較演算子よりも優先順位が低くなります。</span><span class="sxs-lookup"><span data-stu-id="2cf64-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>

- <span data-ttu-id="2cf64-109">優先順位が同じ演算子は、式に出現する順序で左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="2cf64-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>

## <a name="precedence-order"></a><span data-ttu-id="2cf64-110">優先順位</span><span class="sxs-lookup"><span data-stu-id="2cf64-110">Precedence Order</span></span>
 <span data-ttu-id="2cf64-111">演算子は、次の優先順位で評価されます。</span><span class="sxs-lookup"><span data-stu-id="2cf64-111">Operators are evaluated in the following order of precedence:</span></span>

### <a name="await-operator"></a><span data-ttu-id="2cf64-112">Await 演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-112">Await Operator</span></span>
 <span data-ttu-id="2cf64-113">Await</span><span class="sxs-lookup"><span data-stu-id="2cf64-113">Await</span></span>

### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="2cf64-114">算術演算子と連結演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-114">Arithmetic and Concatenation Operators</span></span>
 <span data-ttu-id="2cf64-115">累乗 (`^`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-115">Exponentiation (`^`)</span></span>

 <span data-ttu-id="2cf64-116">単項 id と否定`+`( `–`,)</span><span class="sxs-lookup"><span data-stu-id="2cf64-116">Unary identity and negation (`+`, `–`)</span></span>

 <span data-ttu-id="2cf64-117">乗算および浮動小数点除算 (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-117">Multiplication and floating-point division (`*`, `/`)</span></span>

 <span data-ttu-id="2cf64-118">整数除算 (`\`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-118">Integer division (`\`)</span></span>

 <span data-ttu-id="2cf64-119">モジュール式 (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-119">Modular arithmetic (`Mod`)</span></span>

 <span data-ttu-id="2cf64-120">加算および減算 (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-120">Addition and subtraction (`+`, `–`)</span></span>

 <span data-ttu-id="2cf64-121">文字列連結 (`&`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-121">String concatenation (`&`)</span></span>

 <span data-ttu-id="2cf64-122">算術ビットシフト (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-122">Arithmetic bit shift (`<<`, `>>`)</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="2cf64-123">比較演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-123">Comparison Operators</span></span>
 <span data-ttu-id="2cf64-124">すべての比較演算子`=`( `<>` `<`、、 `<=`、 `>` 、、`IsNot`、 、、、`TypeOf`... `Is` `>=` `Like``Is`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>

### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="2cf64-125">論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-125">Logical and Bitwise Operators</span></span>
 <span data-ttu-id="2cf64-126">否定 (`Not`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-126">Negation (`Not`)</span></span>

 <span data-ttu-id="2cf64-127">(`And`,) `AndAlso`の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="2cf64-127">Conjunction (`And`, `AndAlso`)</span></span>

 <span data-ttu-id="2cf64-128">包括和 (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="2cf64-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>

 <span data-ttu-id="2cf64-129">排他的論理和`Xor`()</span><span class="sxs-lookup"><span data-stu-id="2cf64-129">Exclusive disjunction (`Xor`)</span></span>

### <a name="comments"></a><span data-ttu-id="2cf64-130">コメント</span><span class="sxs-lookup"><span data-stu-id="2cf64-130">Comments</span></span>
 <span data-ttu-id="2cf64-131">`=`演算子は、代入演算子ではなく、等値比較演算子にすぎません。</span><span class="sxs-lookup"><span data-stu-id="2cf64-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="2cf64-132">文字列連結演算子 (`&`) は算術演算子ではありませんが、優先順位は算術演算子でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="2cf64-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>

 <span data-ttu-id="2cf64-133">演算子`Is` と`IsNot`演算子は、オブジェクト参照の比較演算子です。</span><span class="sxs-lookup"><span data-stu-id="2cf64-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="2cf64-134">2つのオブジェクトの値を比較しません。2つのオブジェクト変数が同じオブジェクトインスタンスを参照しているかどうかを確認するだけです。</span><span class="sxs-lookup"><span data-stu-id="2cf64-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>

## <a name="associativity"></a><span data-ttu-id="2cf64-135">結合規則</span><span class="sxs-lookup"><span data-stu-id="2cf64-135">Associativity</span></span>
 <span data-ttu-id="2cf64-136">同じ優先順位の演算子が乗算や除算などの式に一緒に表示される場合、コンパイラは各操作を左から右に検出するたびに評価します。</span><span class="sxs-lookup"><span data-stu-id="2cf64-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="2cf64-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2cf64-137">The following example illustrates this.</span></span>

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 <span data-ttu-id="2cf64-138">最初の式では、除算 96/8 (結果 12) と除算 12/4 が評価されます。これは3つになります。</span><span class="sxs-lookup"><span data-stu-id="2cf64-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="2cf64-139">コンパイラでは、の`n1`操作が左から右に評価されるため、その順序がに`n2`明示的に指定されている場合、評価は同じになります。</span><span class="sxs-lookup"><span data-stu-id="2cf64-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="2cf64-140">`n1` と`n2`の両方に3の結果があります。</span><span class="sxs-lookup"><span data-stu-id="2cf64-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="2cf64-141">これに対し`n3` 、の結果は48です。これは、かっこによってコンパイラによって最初に 8/4 が評価されるためです。</span><span class="sxs-lookup"><span data-stu-id="2cf64-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>

 <span data-ttu-id="2cf64-142">この動作により、Visual Basic では、演算子が*左結合*されていると言います。</span><span class="sxs-lookup"><span data-stu-id="2cf64-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>

## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="2cf64-143">優先順位と結合規則のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="2cf64-143">Overriding Precedence and Associativity</span></span>
 <span data-ttu-id="2cf64-144">かっこを使用して、式の一部の部分を他の式の前に評価するように強制できます。</span><span class="sxs-lookup"><span data-stu-id="2cf64-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="2cf64-145">これにより、優先順位と左結合規則の両方がオーバーライドされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2cf64-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="2cf64-146">Visual Basic は、かっこで囲まれた操作を外部のの前に常に実行します。</span><span class="sxs-lookup"><span data-stu-id="2cf64-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="2cf64-147">ただし、かっこで囲まれている場合は、かっこ内でかっこを使用しない限り、通常の優先順位と結合規則が維持されます。</span><span class="sxs-lookup"><span data-stu-id="2cf64-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="2cf64-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2cf64-148">The following example illustrates this.</span></span>

```vb
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

## <a name="see-also"></a><span data-ttu-id="2cf64-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cf64-149">See also</span></span>

- [<span data-ttu-id="2cf64-150">= 演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="2cf64-151">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="2cf64-152">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="2cf64-153">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="2cf64-154">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="2cf64-155">Await 演算子</span><span class="sxs-lookup"><span data-stu-id="2cf64-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="2cf64-156">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="2cf64-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2cf64-157">演算子および式</span><span class="sxs-lookup"><span data-stu-id="2cf64-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
