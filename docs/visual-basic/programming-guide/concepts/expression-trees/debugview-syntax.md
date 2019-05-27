---
title: DebugView プロパティ (Visual Basic) で使用される構文
description: DebugView プロパティで式ツリーの文字列表現を生成するために使用される特別な構文について説明します
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 1b2a1164f02208cc7578820d8f8ed3bc145fb5b8
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196532"
---
# <a name="debugview-syntax"></a><span data-ttu-id="005f0-103">`DebugView` の構文</span><span class="sxs-lookup"><span data-stu-id="005f0-103">`DebugView` syntax</span></span> 

<span data-ttu-id="005f0-104">`DebugView` (デバッグ時にのみ使用可能な) プロパティを文字列に式ツリーの表示を提供します。</span><span class="sxs-lookup"><span data-stu-id="005f0-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="005f0-105">構文のほとんどは; を理解するとても簡単です。特殊なケースは、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="005f0-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="005f0-106">それぞれの例の後に、コメント ブロックを含む、`DebugView`します。</span><span class="sxs-lookup"><span data-stu-id="005f0-106">Each example is followed by a comment block containing the `DebugView`.</span></span> 

## <a name="parameterexpression"></a><span data-ttu-id="005f0-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="005f0-107">ParameterExpression</span></span>

<span data-ttu-id="005f0-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> 変数名は、先頭に記号 "$" を付けて表示されます。</span><span class="sxs-lookup"><span data-stu-id="005f0-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="005f0-109">パラメーターに名前がない場合、`$var1` や `$var2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="005f0-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="005f0-110">使用例</span><span class="sxs-lookup"><span data-stu-id="005f0-110">Examples</span></span>

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a><span data-ttu-id="005f0-111">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="005f0-111">ConstantExpressions</span></span>

<span data-ttu-id="005f0-112">整数値、文字列、および `null` を表す <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> オブジェクトの場合、定数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="005f0-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="005f0-113">一部の数値型の値に、サフィックスが追加されます。</span><span class="sxs-lookup"><span data-stu-id="005f0-113">For some numeric types, a suffix is added to the value:</span></span>

| <span data-ttu-id="005f0-114">型</span><span class="sxs-lookup"><span data-stu-id="005f0-114">Type</span></span> | <span data-ttu-id="005f0-115">キーワード</span><span class="sxs-lookup"><span data-stu-id="005f0-115">Keyword</span></span> | <span data-ttu-id="005f0-116">サフィックス</span><span class="sxs-lookup"><span data-stu-id="005f0-116">Suffix</span></span> |  
|--|--|--|
| <xref:System.UInt32> | [<span data-ttu-id="005f0-117">UInteger</span><span class="sxs-lookup"><span data-stu-id="005f0-117">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md) | <span data-ttu-id="005f0-118">U</span><span class="sxs-lookup"><span data-stu-id="005f0-118">U</span></span> |
| <xref:System.Int64> | [<span data-ttu-id="005f0-119">Long</span><span class="sxs-lookup"><span data-stu-id="005f0-119">Long</span></span>](../../../language-reference/data-types/long-data-type.md) | <span data-ttu-id="005f0-120">L</span><span class="sxs-lookup"><span data-stu-id="005f0-120">L</span></span> |
| <xref:System.UInt64> | [<span data-ttu-id="005f0-121">ULong</span><span class="sxs-lookup"><span data-stu-id="005f0-121">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md) | <span data-ttu-id="005f0-122">UL</span><span class="sxs-lookup"><span data-stu-id="005f0-122">UL</span></span> |
| <xref:System.Double> | [<span data-ttu-id="005f0-123">Double</span><span class="sxs-lookup"><span data-stu-id="005f0-123">Double</span></span>](../../../language-reference/data-types/double-data-type.md) | <span data-ttu-id="005f0-124">D</span><span class="sxs-lookup"><span data-stu-id="005f0-124">D</span></span> |
| <xref:System.Single> | [<span data-ttu-id="005f0-125">Single</span><span class="sxs-lookup"><span data-stu-id="005f0-125">Single</span></span>](../../../language-reference/data-types/single-data-type.md) | <span data-ttu-id="005f0-126">F</span><span class="sxs-lookup"><span data-stu-id="005f0-126">F</span></span> | 
| <xref:System.Decimal> | [<span data-ttu-id="005f0-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="005f0-127">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md) | <span data-ttu-id="005f0-128">M</span><span class="sxs-lookup"><span data-stu-id="005f0-128">M</span></span> |

### <a name="examples"></a><span data-ttu-id="005f0-129">使用例</span><span class="sxs-lookup"><span data-stu-id="005f0-129">Examples</span></span>

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a><span data-ttu-id="005f0-130">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="005f0-130">BlockExpression</span></span>

<span data-ttu-id="005f0-131">場合の種類、<xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType>オブジェクトは、ブロックの最後の式の型とは異なる、山かっこ内で、型が表示されます (`<`と`>`)。</span><span class="sxs-lookup"><span data-stu-id="005f0-131">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="005f0-132">それ以外の場合、<xref:System.Linq.Expressions.BlockExpression> オブジェクトの型は表示されません。</span><span class="sxs-lookup"><span data-stu-id="005f0-132">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="005f0-133">使用例</span><span class="sxs-lookup"><span data-stu-id="005f0-133">Examples</span></span>

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object), 
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a><span data-ttu-id="005f0-134">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="005f0-134">LambdaExpression</span></span>

<span data-ttu-id="005f0-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> オブジェクトは、デリゲート型と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="005f0-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="005f0-136">ラムダ式に名前がない場合、`#Lambda1` や `#Lambda2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="005f0-136">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="005f0-137">使用例</span><span class="sxs-lookup"><span data-stu-id="005f0-137">Examples</span></span>

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a><span data-ttu-id="005f0-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="005f0-138">LabelExpression</span></span>

<span data-ttu-id="005f0-139"><xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> オブジェクトの既定値を指定した場合、その値が <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> オブジェクトの前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="005f0-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="005f0-140">`.Label` トークンは、ラベルの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="005f0-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="005f0-141">`.LabelTarget` トークンは、ジャンプ先のターゲットを示します。</span><span class="sxs-lookup"><span data-stu-id="005f0-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="005f0-142">ラベルに名前がない場合、`#Label1` や `#Label2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="005f0-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="005f0-143">使用例</span><span class="sxs-lookup"><span data-stu-id="005f0-143">Examples</span></span>

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), 
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a><span data-ttu-id="005f0-144">checked 演算子</span><span class="sxs-lookup"><span data-stu-id="005f0-144">Checked Operators</span></span>

<span data-ttu-id="005f0-145">Checked 演算子はと共に表示されます、`#`シンボル、演算子の前にします。</span><span class="sxs-lookup"><span data-stu-id="005f0-145">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="005f0-146">たとえば、checked 加算演算子は `#+` と表示されます。</span><span class="sxs-lookup"><span data-stu-id="005f0-146">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="005f0-147">使用例</span><span class="sxs-lookup"><span data-stu-id="005f0-147">Examples</span></span>

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```