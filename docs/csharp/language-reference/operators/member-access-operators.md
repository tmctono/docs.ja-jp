---
title: メンバー アクセス演算子 - C# リファレンス
description: 型のメンバーにアクセスするために使用できる C# 演算子について説明します。
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: 763fdb442fa0037dafd51f89badd04436e24d254
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566834"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="1d4c7-103">メンバー アクセス演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1d4c7-103">Member access operators (C# reference)</span></span>

<span data-ttu-id="1d4c7-104">型のメンバーにアクセスするときは、次の演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="1d4c7-105">[`.` (メンバー アクセス) ](#member-access-operator-): 名前空間または型のメンバーにアクセスします</span><span class="sxs-lookup"><span data-stu-id="1d4c7-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="1d4c7-106">[`[]` (配列要素またはインデクサー アクセス) ](#indexer-operator-): 配列要素または型のインデクサーにアクセスします</span><span class="sxs-lookup"><span data-stu-id="1d4c7-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="1d4c7-107">[`?.` および `?[]` (null 条件演算子)](#null-conditional-operators--and-): オペランドが null でない場合にのみ、メンバーまたは要素へのアクセス操作を実行します</span><span class="sxs-lookup"><span data-stu-id="1d4c7-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="1d4c7-108">[`()` (呼び出し)](#invocation-operator-): アクセスしたメソッドを呼び出すか、デリゲートを呼び出します</span><span class="sxs-lookup"><span data-stu-id="1d4c7-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="1d4c7-109">メンバー アクセス演算子 .</span><span class="sxs-lookup"><span data-stu-id="1d4c7-109">Member access operator .</span></span>

<span data-ttu-id="1d4c7-110">以下の例に示すように、名前空間のメンバーまたは型にアクセスするために `.` トークンを使います。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-110">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="1d4c7-111">次の [`using` ディレクティブ](../keywords/using-directive.md)の例に示すように、`.` を使って、名前空間内の入れ子になった名前空間にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-111">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="1d4c7-112">次のコードに示すように、`.` を使って "*修飾名*" を作成して名前空間内の型にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-112">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="1d4c7-113">[`using` ディレクティブ](../keywords/using-directive.md)を使い、必要に応じて修飾名を利用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-113">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="1d4c7-114">次のコードに示すように、`.` を使って、[型のメンバー](../../programming-guide/classes-and-structs/index.md#members) (静的および非静的) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-114">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="1d4c7-115">また、`.` を使って[拡張メソッド](../../programming-guide/classes-and-structs/extension-methods.md)にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-115">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="1d4c7-116">インデクサー演算子 []</span><span class="sxs-lookup"><span data-stu-id="1d4c7-116">Indexer operator []</span></span>

<span data-ttu-id="1d4c7-117">通常、角かっこ `[]` は、配列、インデクサー、またはポインター要素へのアクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-117">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="1d4c7-118">配列へのアクセス</span><span class="sxs-lookup"><span data-stu-id="1d4c7-118">Array access</span></span>

<span data-ttu-id="1d4c7-119">次の例は、配列要素へのアクセス方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-119">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="1d4c7-120">配列インデックスが配列の対応するディメンションの範囲に含まれない場合、<xref:System.IndexOutOfRangeException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-120">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="1d4c7-121">前述の例が示すように、配列型の宣言と配列インスタンスのインスタンス化にも角かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-121">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="1d4c7-122">配列の詳細については、「[配列](../../programming-guide/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-122">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="1d4c7-123">インデクサーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="1d4c7-123">Indexer access</span></span>

<span data-ttu-id="1d4c7-124">次の例では、インデクサーへのアクセスを示すために .NET <xref:System.Collections.Generic.Dictionary%602> 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-124">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="1d4c7-125">インデクサーを使用すると、配列のインデックス作成と同様の方法でユーザー定義型のインスタンスのインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-125">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="1d4c7-126">整数である必要がある配列インデックスとは異なり、任意の型を持つインデクサー引数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-126">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="1d4c7-127">インデクサーの詳細については、「[インデクサー](../../programming-guide/indexers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-127">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="1d4c7-128">[] の他の使用方法</span><span class="sxs-lookup"><span data-stu-id="1d4c7-128">Other usages of []</span></span>

<span data-ttu-id="1d4c7-129">ポインター要素へのアクセスの詳細については、[ポインターに関連する演算子](pointer-related-operators.md)に関する記事の「[ポインター要素アクセス演算子 []](pointer-related-operators.md#pointer-element-access-operator-)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-129">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="1d4c7-130">角かっこは、[属性](../../programming-guide/concepts/attributes/index.md)を指定するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-130">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="1d4c7-131">Null 条件演算子 ?.</span><span class="sxs-lookup"><span data-stu-id="1d4c7-131">Null-conditional operators ?.</span></span> <span data-ttu-id="1d4c7-132">および ?[]</span><span class="sxs-lookup"><span data-stu-id="1d4c7-132">and ?[]</span></span>

<span data-ttu-id="1d4c7-133">C# 6 以降で使用できる Null 条件付き演算子は、そのオペランドが null 以外と評価された場合にのみ、オペランドにメンバー アクセス操作 (`?.`) または要素アクセス操作 (`?[]`) を適用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-133">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="1d4c7-134">オペランドが `null` と評価された場合、演算子を適用した結果は `null` です。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-134">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span> <span data-ttu-id="1d4c7-135">Null 条件メンバー アクセス演算子 `?.` は Elvis 演算子とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-135">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

<span data-ttu-id="1d4c7-136">Null 条件演算子はショートサーキットです。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-136">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="1d4c7-137">つまり、条件付きのメンバーまたは要素アクセス操作のチェーン内にある 1 つの操作から `null` が返された場合、残りのチェーンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-137">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="1d4c7-138">次の例では、`A` が `null` と評価されると `B` は評価されず、`A` または `B` が `null` と評価されると `C` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-138">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="1d4c7-139">`?.` および `?[]` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-139">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="1d4c7-140">前述の例では、[NULL 合体演算子](null-coalescing-operator.md)の使用方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-140">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="1d4c7-141">NULL 合体演算子は、NULL 条件演算の結果が `null` の場合に評価する代替の式を指定するために使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-141">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="1d4c7-142">スレッドセーフなデリゲートの呼び出し</span><span class="sxs-lookup"><span data-stu-id="1d4c7-142">Thread-safe delegate invocation</span></span>

<span data-ttu-id="1d4c7-143">次のコードに示すように、`?.` 演算子を使用してデリゲートが null 以外かどうかを確認し、それをスレッドセーフな方法で呼び出します (たとえば、[イベントを発生させる](../../../standard/events/how-to-raise-and-consume-events.md)場合)。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-143">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="1d4c7-144">このコードは、C# 5 以前で使用する次のコードと同等です。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-144">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="1d4c7-145">呼び出し演算子 ()</span><span class="sxs-lookup"><span data-stu-id="1d4c7-145">Invocation operator ()</span></span>

<span data-ttu-id="1d4c7-146">かっこ `()` は、[メソッド](../../programming-guide/classes-and-structs/methods.md)を呼び出すとき、または[デリゲート](../../programming-guide/delegates/index.md)を呼び出すときに使用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-146">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="1d4c7-147">メソッドを呼び出す方法 (引数を指定した場合と指定しない場合) とデリゲートを呼び出す方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-147">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="1d4c7-148">かっこは、[`new`](new-operator.md) 演算子を使用して[コンストラクター](../../programming-guide/classes-and-structs/constructors.md)を呼び出すときにも使用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-148">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="1d4c7-149">() の他の使用方法</span><span class="sxs-lookup"><span data-stu-id="1d4c7-149">Other usages of ()</span></span>

<span data-ttu-id="1d4c7-150">式に含まれる演算を評価する順序を指定する場合にもかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-150">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="1d4c7-151">詳細については、「[演算子](../../programming-guide/statements-expressions-operators/operators.md)」記事の「[かっこの追加](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-151">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="1d4c7-152">優先順位順に並べられた演算子の一覧については、「[C# 演算子](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-152">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

<span data-ttu-id="1d4c7-153">明示的な型変換を実行する[キャスト式](type-testing-and-cast.md#cast-operator-)でも、かっこが使われます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-153">[Cast expressions](type-testing-and-cast.md#cast-operator-), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="1d4c7-154">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="1d4c7-154">Operator overloadability</span></span>

<span data-ttu-id="1d4c7-155">`.` および `()` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-155">The `.` and `()` operators cannot be overloaded.</span></span> <span data-ttu-id="1d4c7-156">`[]` 演算子も、オーバーロードできない演算子と見なされます。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-156">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="1d4c7-157">ユーザー定義型を使用したインデックス作成をサポートするには、[インデクサー](../../programming-guide/indexers/index.md)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-157">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1d4c7-158">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="1d4c7-158">C# language specification</span></span>

<span data-ttu-id="1d4c7-159">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d4c7-159">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="1d4c7-160">メンバー アクセス</span><span class="sxs-lookup"><span data-stu-id="1d4c7-160">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="1d4c7-161">要素アクセス</span><span class="sxs-lookup"><span data-stu-id="1d4c7-161">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="1d4c7-162">NULL 条件演算子</span><span class="sxs-lookup"><span data-stu-id="1d4c7-162">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="1d4c7-163">呼び出し式</span><span class="sxs-lookup"><span data-stu-id="1d4c7-163">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="1d4c7-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d4c7-164">See also</span></span>

- [<span data-ttu-id="1d4c7-165">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1d4c7-165">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1d4c7-166">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="1d4c7-166">C# operators</span></span>](index.md)
- [<span data-ttu-id="1d4c7-167">?? (Null 合体演算子)</span><span class="sxs-lookup"><span data-stu-id="1d4c7-167">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="1d4c7-168">:: 演算子</span><span class="sxs-lookup"><span data-stu-id="1d4c7-168">:: operator</span></span>](namespace-alias-qualifier.md)
