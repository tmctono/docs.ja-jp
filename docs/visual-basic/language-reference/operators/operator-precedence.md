---
title: 演算子の優先順位
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
ms.openlocfilehash: eef6314f5fc1f5a7fffa7997559f697130f6f755
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401447"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="d910c-102">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="d910c-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="d910c-103">式で複数の演算が行われると、各部分は "*演算子の優先順位*" と呼ばれる事前に定義された順序で評価および解決されます。</span><span class="sxs-lookup"><span data-stu-id="d910c-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>

## <a name="precedence-rules"></a><span data-ttu-id="d910c-104">優先順位の規則</span><span class="sxs-lookup"><span data-stu-id="d910c-104">Precedence Rules</span></span>
 <span data-ttu-id="d910c-105">式に複数のカテゴリの演算子が含まれている場合は、次の規則に従って評価されます。</span><span class="sxs-lookup"><span data-stu-id="d910c-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>

- <span data-ttu-id="d910c-106">算術演算子と連結演算子には、次のセクションで説明する優先順位があり、これらはすべて比較演算子、論理演算子、ビット演算子よりも優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="d910c-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>

- <span data-ttu-id="d910c-107">すべての比較演算子は同じ優先順位を持ち、論理演算子とビット演算子より優先順位が高くなりますが、算術演算子と連結演算子より優先順位が低くなります。</span><span class="sxs-lookup"><span data-stu-id="d910c-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>

- <span data-ttu-id="d910c-108">論理演算子とビット演算子には、次のセクションで説明する優先順位があり、これらはすべて算術演算子、連結演算子、比較演算子よりも優先順位が低くなります。</span><span class="sxs-lookup"><span data-stu-id="d910c-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>

- <span data-ttu-id="d910c-109">優先順位が同じ演算子は、式に出現する順序で左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="d910c-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>

## <a name="precedence-order"></a><span data-ttu-id="d910c-110">優先順位</span><span class="sxs-lookup"><span data-stu-id="d910c-110">Precedence Order</span></span>
 <span data-ttu-id="d910c-111">演算子は次の優先順位で評価されます。</span><span class="sxs-lookup"><span data-stu-id="d910c-111">Operators are evaluated in the following order of precedence:</span></span>

### <a name="await-operator"></a><span data-ttu-id="d910c-112">Await 演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-112">Await Operator</span></span>
 <span data-ttu-id="d910c-113">Await</span><span class="sxs-lookup"><span data-stu-id="d910c-113">Await</span></span>

### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="d910c-114">算術演算子と連結演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-114">Arithmetic and Concatenation Operators</span></span>
 <span data-ttu-id="d910c-115">累乗 (`^`)</span><span class="sxs-lookup"><span data-stu-id="d910c-115">Exponentiation (`^`)</span></span>

 <span data-ttu-id="d910c-116">単項恒等と否定 (`+`、`–`)</span><span class="sxs-lookup"><span data-stu-id="d910c-116">Unary identity and negation (`+`, `–`)</span></span>

 <span data-ttu-id="d910c-117">乗算および浮動小数点除算 (`*`、`/`)</span><span class="sxs-lookup"><span data-stu-id="d910c-117">Multiplication and floating-point division (`*`, `/`)</span></span>

 <span data-ttu-id="d910c-118">整数の除算 (`\`)</span><span class="sxs-lookup"><span data-stu-id="d910c-118">Integer division (`\`)</span></span>

 <span data-ttu-id="d910c-119">モジュラー演算 (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="d910c-119">Modular arithmetic (`Mod`)</span></span>

 <span data-ttu-id="d910c-120">加算と減算 (`+`、`–`)</span><span class="sxs-lookup"><span data-stu-id="d910c-120">Addition and subtraction (`+`, `–`)</span></span>

 <span data-ttu-id="d910c-121">文字列連結 (`&`)</span><span class="sxs-lookup"><span data-stu-id="d910c-121">String concatenation (`&`)</span></span>

 <span data-ttu-id="d910c-122">算術ビット シフト (`<<`、`>>`)</span><span class="sxs-lookup"><span data-stu-id="d910c-122">Arithmetic bit shift (`<<`, `>>`)</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="d910c-123">比較演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-123">Comparison Operators</span></span>
 <span data-ttu-id="d910c-124">すべての比較演算子 (`=`、`<>`、`<`、`<=`、`>`、`>=`、`Is`、`IsNot`、`Like`、`TypeOf`...`Is`)</span><span class="sxs-lookup"><span data-stu-id="d910c-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>

### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="d910c-125">論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-125">Logical and Bitwise Operators</span></span>
 <span data-ttu-id="d910c-126">否定 (`Not`)</span><span class="sxs-lookup"><span data-stu-id="d910c-126">Negation (`Not`)</span></span>

 <span data-ttu-id="d910c-127">接続詞 (`And`、`AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="d910c-127">Conjunction (`And`, `AndAlso`)</span></span>

 <span data-ttu-id="d910c-128">包含的論理和 (`Or`、`OrElse`)</span><span class="sxs-lookup"><span data-stu-id="d910c-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>

 <span data-ttu-id="d910c-129">排他的論理和 (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="d910c-129">Exclusive disjunction (`Xor`)</span></span>

### <a name="comments"></a><span data-ttu-id="d910c-130">コメント</span><span class="sxs-lookup"><span data-stu-id="d910c-130">Comments</span></span>
 <span data-ttu-id="d910c-131">`=` 演算子は単に等値比較演算子であり、代入演算子ではありません。</span><span class="sxs-lookup"><span data-stu-id="d910c-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="d910c-132">文字列連結演算子 (`&`) は算術演算子ではありませんが、優先順位においては算術演算子と同じグループに分類されます。</span><span class="sxs-lookup"><span data-stu-id="d910c-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>

 <span data-ttu-id="d910c-133">`Is` と `IsNot` の演算子は、オブジェクト参照比較演算子です。</span><span class="sxs-lookup"><span data-stu-id="d910c-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="d910c-134">これらは 2つのオブジェクトの値を比較しません。2 つのオブジェクト変数が同じオブジェクト インスタンスを参照するかどうかを確認するだけです。</span><span class="sxs-lookup"><span data-stu-id="d910c-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>

## <a name="associativity"></a><span data-ttu-id="d910c-135">結合規則</span><span class="sxs-lookup"><span data-stu-id="d910c-135">Associativity</span></span>
 <span data-ttu-id="d910c-136">同じ優先順位の演算子が乗算や除算などの式に一緒に現れる場合、コンパイラは各演算の出現時にそれを左から右に評価します。</span><span class="sxs-lookup"><span data-stu-id="d910c-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="d910c-137">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="d910c-137">The following example illustrates this.</span></span>

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 <span data-ttu-id="d910c-138">最初の式では、除算 96/8 (結果は 12) が評価され、次に除算 12/4 (結果は 3) が評価されます。</span><span class="sxs-lookup"><span data-stu-id="d910c-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="d910c-139">コンパイラでは `n1` の演算が左から右に評価されるため、その順序が `n2` に明示的に指定されている場合、評価は同じになります。</span><span class="sxs-lookup"><span data-stu-id="d910c-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="d910c-140">`n1` と `n2` の両方の結果が 3 になります。</span><span class="sxs-lookup"><span data-stu-id="d910c-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="d910c-141">これに対して、`n3` の結果は 48 になります。これは、かっこによりコンパイラで 8/4 が最初に評価されるためです。</span><span class="sxs-lookup"><span data-stu-id="d910c-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>

 <span data-ttu-id="d910c-142">この動作のため、演算子は Visual Basic 内で "*結合規則が左から右*" であると言われます。</span><span class="sxs-lookup"><span data-stu-id="d910c-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>

## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="d910c-143">優先順位と結合規則のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="d910c-143">Overriding Precedence and Associativity</span></span>
 <span data-ttu-id="d910c-144">かっこを使用して、式のいくつかの部分を他の部分より前に強制的に評価できます。</span><span class="sxs-lookup"><span data-stu-id="d910c-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="d910c-145">これにより、優先順位と左から右の結合規則の両方をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="d910c-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="d910c-146">Visual Basic では常に、かっこで囲まれた演算がその外側にある演算より前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d910c-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="d910c-147">ただし、かっこで内では、通常の優先順位と結合規則が維持されます (かっこ内でかっこを使用する場合は除く)。</span><span class="sxs-lookup"><span data-stu-id="d910c-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="d910c-148">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="d910c-148">The following example illustrates this.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d910c-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="d910c-149">See also</span></span>

- [<span data-ttu-id="d910c-150">= 演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-150">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="d910c-151">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-151">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="d910c-152">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-152">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="d910c-153">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-153">Like Operator</span></span>](like-operator.md)
- [<span data-ttu-id="d910c-154">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-154">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="d910c-155">Await 演算子</span><span class="sxs-lookup"><span data-stu-id="d910c-155">Await Operator</span></span>](await-operator.md)
- [<span data-ttu-id="d910c-156">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="d910c-156">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="d910c-157">演算子および式</span><span class="sxs-lookup"><span data-stu-id="d910c-157">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
