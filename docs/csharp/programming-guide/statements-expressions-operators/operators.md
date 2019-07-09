---
title: 演算子 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 551d4cd8bf26a1c1caf3cbf611d9f338ae2581be
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609503"
---
# <a name="operators-c-programming-guide"></a><span data-ttu-id="418a6-102">演算子 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="418a6-102">Operators (C# Programming Guide)</span></span>

<span data-ttu-id="418a6-103">C# では、 *演算子* は式またはステートメントの中で 1 つ以上の *オペランド* に適用されるプログラム要素です。</span><span class="sxs-lookup"><span data-stu-id="418a6-103">In C#, an *operator* is a program element that is applied to one or more *operands* in an expression or statement.</span></span> <span data-ttu-id="418a6-104">インクリメント演算子 (`++`) や `new`など、1 つのオペランドを受け取る演算子を *単項* 演算子と言います。</span><span class="sxs-lookup"><span data-stu-id="418a6-104">Operators that take one operand, such as the increment operator (`++`) or `new`, are referred to as *unary* operators.</span></span> <span data-ttu-id="418a6-105">算術演算子 (`+`、`-`、`*`、`/`) など、2 つのオペランドを受け取る演算子を *二項* 演算子と言います。</span><span class="sxs-lookup"><span data-stu-id="418a6-105">Operators that take two operands, such as arithmetic operators (`+`,`-`,`*`,`/`), are referred to as *binary* operators.</span></span> <span data-ttu-id="418a6-106">条件演算子 (`?:`) は、3 つのオペランドを受け取る、C# でただ 1 つの三項演算子です。</span><span class="sxs-lookup"><span data-stu-id="418a6-106">One operator, the conditional operator (`?:`), takes three operands and is the sole ternary operator in C#.</span></span>  
  
 <span data-ttu-id="418a6-107">次の C# ステートメントには、1 つの単項演算子と 1 つのオペランドがあります。</span><span class="sxs-lookup"><span data-stu-id="418a6-107">The following C# statement contains a single unary operator and a single operand.</span></span> <span data-ttu-id="418a6-108">インクリメント演算子 `++`は、オペランド `y`の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="418a6-108">The increment operator, `++`, modifies the value of the operand `y`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 <span data-ttu-id="418a6-109">次の C# ステートメントには、それぞれ 2 つのオペランドを持つ 2 つの二項演算子があります。</span><span class="sxs-lookup"><span data-stu-id="418a6-109">The following C# statement contains two binary operators, each with two operands.</span></span> <span data-ttu-id="418a6-110">代入演算子 `=`には、オペランドとして整数の変数 `y` と式 `2 + 3` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="418a6-110">The assignment operator, `=`, has the integer variable `y` and the expression `2 + 3` as operands.</span></span> <span data-ttu-id="418a6-111">式 `2 + 3` 自体も、加算演算子と、2 つのオペランド ( `2` と `3`) で構成されています。</span><span class="sxs-lookup"><span data-stu-id="418a6-111">The expression `2 + 3` itself consists of the addition operator and two operands, `2` and `3`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
<span data-ttu-id="418a6-112">オペランドは、任意の長さのコードで構成される有効な式で、任意の数の副次式を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="418a6-112">An operand can be a valid expression that is composed of any length of code, and it can comprise any number of sub expressions.</span></span> <span data-ttu-id="418a6-113">複数の演算子を含む式の場合、演算子が適用される順序は *演算子の優先順位*、 *結合規則*、およびかっこによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-113">In an expression that contains multiple operators, the order in which the operators are applied is determined by *operator precedence*, *associativity*, and parentheses.</span></span>  

## <a name="operator-precedence"></a><span data-ttu-id="418a6-114">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="418a6-114">Operator precedence</span></span>
  
<span data-ttu-id="418a6-115">各演算子には優先順位が定義されています。</span><span class="sxs-lookup"><span data-stu-id="418a6-115">Each operator has a defined precedence.</span></span> <span data-ttu-id="418a6-116">優先順位のレベルが異なる複数の演算子を含む式の場合、演算子の優先順位によって演算子が評価される順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-116">In an expression that contains multiple operators that have different precedence levels, the precedence of the operators determines the order in which the operators are evaluated.</span></span> <span data-ttu-id="418a6-117">たとえば、次のステートメントでは `n1` に 3 が代入されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-117">For example, the following statement assigns 3 to `n1`:</span></span>

```csharp
n1 = 11 - 2 * 4;
```

<span data-ttu-id="418a6-118">乗算は減算よりも優先順位が高いため、最初に乗算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-118">The multiplication is executed first because multiplication takes precedence over subtraction.</span></span>

<span data-ttu-id="418a6-119">優先度順に並べられた C# 演算子の完全な一覧については、「[C# 演算子](../../language-reference/operators/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="418a6-119">For the complete list of C# operators ordered by precedence level, see [C# operators](../../language-reference/operators/index.md).</span></span>
  
## <a name="associativity"></a><span data-ttu-id="418a6-120">結合規則</span><span class="sxs-lookup"><span data-stu-id="418a6-120">Associativity</span></span>

 <span data-ttu-id="418a6-121">1 つの式に同じ優先順位の演算子が複数個含まれている場合、それらの演算子は結合規則に基づいて評価されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-121">When two or more operators that have the same precedence are present in an expression, they are evaluated based on associativity.</span></span> <span data-ttu-id="418a6-122">結合規則が左から右の演算子は、左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-122">Left-associative operators are evaluated in order from left to right.</span></span> <span data-ttu-id="418a6-123">たとえば、 `x * y / z` は `(x * y) / z`と評価されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-123">For example, `x * y / z` is evaluated as `(x * y) / z`.</span></span> <span data-ttu-id="418a6-124">結合規則が右から左の演算子は、右から左に評価されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-124">Right-associative operators are evaluated in order from right to left.</span></span> <span data-ttu-id="418a6-125">たとえば、代入演算子は結合規則が右から左です。</span><span class="sxs-lookup"><span data-stu-id="418a6-125">For example, the assignment operator is right associative.</span></span> <span data-ttu-id="418a6-126">そうでない場合、次のコードはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="418a6-126">If it were not, the following code would result in an error.</span></span>  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 <span data-ttu-id="418a6-127">別の例として、三項演算子 ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) は、結合規則が右から左です。</span><span class="sxs-lookup"><span data-stu-id="418a6-127">As another example the ternary operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) is right associative.</span></span> <span data-ttu-id="418a6-128">ほとんどの二項演算子は結合関係が左から右です。</span><span class="sxs-lookup"><span data-stu-id="418a6-128">Most binary operators are left associative.</span></span>  
  
 <span data-ttu-id="418a6-129">式に含まれる演算子の結合規則が左から右であっても、右から左であっても、各式のオペランドは初めに左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="418a6-129">Whether the operators in an expression are left associative or right associative, the operands of each expression are evaluated first, from left to right.</span></span> <span data-ttu-id="418a6-130">次の例では、演算子とオペランドの評価の順序について示します。</span><span class="sxs-lookup"><span data-stu-id="418a6-130">The following examples illustrate the order of evaluation of operators and operands.</span></span>  
  
|<span data-ttu-id="418a6-131">ステートメント</span><span class="sxs-lookup"><span data-stu-id="418a6-131">Statement</span></span>|<span data-ttu-id="418a6-132">評価の順序</span><span class="sxs-lookup"><span data-stu-id="418a6-132">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = b`|<span data-ttu-id="418a6-133">a、b、=</span><span class="sxs-lookup"><span data-stu-id="418a6-133">a, b, =</span></span>|  
|`a = b + c`|<span data-ttu-id="418a6-134">a、b、c、+、=</span><span class="sxs-lookup"><span data-stu-id="418a6-134">a, b, c, +, =</span></span>|  
|`a = b + c * d`|<span data-ttu-id="418a6-135">a、b、c、d、\*、+、=</span><span class="sxs-lookup"><span data-stu-id="418a6-135">a, b, c, d, \*, +, =</span></span>|  
|`a = b * c + d`|<span data-ttu-id="418a6-136">a、b、c、\*、d、+、=</span><span class="sxs-lookup"><span data-stu-id="418a6-136">a, b, c, \*, d, +, =</span></span>|  
|`a = b - c + d`|<span data-ttu-id="418a6-137">a、b、c、-、d、+、=</span><span class="sxs-lookup"><span data-stu-id="418a6-137">a, b, c, -, d, +, =</span></span>|  
|`a += b -= c`|<span data-ttu-id="418a6-138">a、b、c、-=、+=</span><span class="sxs-lookup"><span data-stu-id="418a6-138">a, b, c, -=, +=</span></span>|  
  
## <a name="adding-parentheses"></a><span data-ttu-id="418a6-139">かっこの追加</span><span class="sxs-lookup"><span data-stu-id="418a6-139">Adding parentheses</span></span>

 <span data-ttu-id="418a6-140">かっこを使用すると、演算子の優先順位と結合規則によって定められた順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="418a6-140">You can change the order imposed by operator precedence and associativity by using parentheses.</span></span> <span data-ttu-id="418a6-141">たとえば、 `2 + 3 * 2` は通常、8 と評価されます。乗算演算子の方が加法演算子よりも優先順位が高いからです。</span><span class="sxs-lookup"><span data-stu-id="418a6-141">For example, `2 + 3 * 2` ordinarily evaluates to 8, because multiplicative operators take precedence over additive operators.</span></span> <span data-ttu-id="418a6-142">しかし、この式を `(2 + 3) * 2`と記述すると、加算の方が乗算よりも先に評価され、結果は 10 になります。</span><span class="sxs-lookup"><span data-stu-id="418a6-142">However, if you write the expression as `(2 + 3) * 2`, the addition is evaluated before the multiplication, and the result is 10.</span></span> <span data-ttu-id="418a6-143">次の例では、かっこを使用した式での評価の順序について示します。</span><span class="sxs-lookup"><span data-stu-id="418a6-143">The following examples illustrate the order of evaluation in parenthesized expressions.</span></span> <span data-ttu-id="418a6-144">前の例では、演算子が適用される前にオペランドが評価されていました。</span><span class="sxs-lookup"><span data-stu-id="418a6-144">As in previous examples, the operands are evaluated before the operator is applied.</span></span>  
  
|<span data-ttu-id="418a6-145">ステートメント</span><span class="sxs-lookup"><span data-stu-id="418a6-145">Statement</span></span>|<span data-ttu-id="418a6-146">評価の順序</span><span class="sxs-lookup"><span data-stu-id="418a6-146">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = (b + c) * d`|<span data-ttu-id="418a6-147">a、b、c、+、d、\*、=</span><span class="sxs-lookup"><span data-stu-id="418a6-147">a, b, c, +, d, \*, =</span></span>|  
|`a = b - (c + d)`|<span data-ttu-id="418a6-148">a、b、c、d、+、-、=</span><span class="sxs-lookup"><span data-stu-id="418a6-148">a, b, c, d, +, -, =</span></span>|  
|`a = (b + c) * (d - e)`|<span data-ttu-id="418a6-149">a、b、c、+、d、e、-、\*、=</span><span class="sxs-lookup"><span data-stu-id="418a6-149">a, b, c, +, d, e, -, \*, =</span></span>|  
  
## <a name="operator-overloading"></a><span data-ttu-id="418a6-150">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="418a6-150">Operator overloading</span></span>

<span data-ttu-id="418a6-151">カスタム クラスやカスタム構造体では、特定の演算子の動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="418a6-151">You can define the behavior of certain operators for custom classes and structs.</span></span> <span data-ttu-id="418a6-152">このプロセスは *演算子のオーバーロード*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="418a6-152">This process is referred to as *operator overloading*.</span></span> <span data-ttu-id="418a6-153">詳細については、「[演算子のオーバーロード](../../language-reference/operators/operator-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="418a6-153">For more information, see [Operator overloading](../../language-reference/operators/operator-overloading.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="418a6-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="418a6-154">See also</span></span>

- [<span data-ttu-id="418a6-155">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="418a6-155">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="418a6-156">ステートメント、式、および演算子</span><span class="sxs-lookup"><span data-stu-id="418a6-156">Statements, Expressions, and Operators</span></span>](index.md)
- [<span data-ttu-id="418a6-157">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="418a6-157">C# Operators</span></span>](../../language-reference/operators/index.md)
