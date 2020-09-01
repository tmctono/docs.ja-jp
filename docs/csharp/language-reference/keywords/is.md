---
description: is - C# リファレンス
title: is - C# リファレンス
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 3508f08857f88fd34478f968a71bae0121d54d1c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134511"
---
# <a name="is-c-reference"></a><span data-ttu-id="647d5-103">is (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="647d5-103">is (C# Reference)</span></span>

<span data-ttu-id="647d5-104">`is` 演算子では、式の結果と指定された型との間に互換性があるかどうかが確認されるか、または (C# 7.0 以降では) パターンに対して式がテストされます。</span><span class="sxs-lookup"><span data-stu-id="647d5-104">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="647d5-105">型テストの `is` 演算子について詳しくは、[型テストとキャスト演算子](../operators/type-testing-and-cast.md)に関する記事の「[is 演算子](../operators/type-testing-and-cast.md#is-operator)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="647d5-105">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="647d5-106">`is` を使用したパターン マッチング</span><span class="sxs-lookup"><span data-stu-id="647d5-106">Pattern matching with `is`</span></span>

<span data-ttu-id="647d5-107">C# 7.0 以降では、`is` および [switch](switch.md) ステートメントでパターン マッチングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="647d5-107">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="647d5-108">`is` キーワードでは、以下のパターンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="647d5-108">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="647d5-109">[型パターン](#type-pattern)では、式を指定された型に変換できるかどうかがテストされ、変換できる場合はその型の変数にキャストされます。</span><span class="sxs-lookup"><span data-stu-id="647d5-109">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="647d5-110">[定数パターン](#constant-pattern): 式の評価が指定された定数値になるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="647d5-110">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="647d5-111">[var パターン](#var-pattern): 照合が常に成功し、式の値が新しいローカル変数にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="647d5-111">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="647d5-112">型パターン</span><span class="sxs-lookup"><span data-stu-id="647d5-112">Type pattern</span></span>

<span data-ttu-id="647d5-113">型パターンを使用してパターン マッチングを実行すると、式を指定された型に変換できるかどうかが `is` によってテストされ、変換できる場合はその型の変数にキャストされます。</span><span class="sxs-lookup"><span data-stu-id="647d5-113">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="647d5-114">`is` ステートメントのわかりやすい拡張機能であり、型の評価および変換を簡潔に記述できます。</span><span class="sxs-lookup"><span data-stu-id="647d5-114">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="647d5-115">`is` 型パターンの一般的な形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="647d5-115">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="647d5-116">ここで *expr* は何らかの型のインスタンスに評価される式、*type* は *expr* の結果が変換される型の名前、*varname* は `is` のテスト結果が `true` である場合に *expr* の結果が変換されるオブジェクトをそれぞれ表しています。</span><span class="sxs-lookup"><span data-stu-id="647d5-116">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="647d5-117">*expr* が `null` ではなく、以下のいずれかの条件が true である場合に `is` 式は `true` となります。</span><span class="sxs-lookup"><span data-stu-id="647d5-117">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="647d5-118">*expr* が *type* と同じ型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="647d5-118">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="647d5-119">*expr* が *type* から派生した型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="647d5-119">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="647d5-120">つまり、*expr* の結果を *type* のインスタンスにアップキャストできる。</span><span class="sxs-lookup"><span data-stu-id="647d5-120">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="647d5-121">*expr* のコンパイル時の型が *type* の基底クラスであり、*expr* の実行時の型が *type* または *type* から派生した型である。</span><span class="sxs-lookup"><span data-stu-id="647d5-121">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="647d5-122">変数の "*コンパイル時の型*" とは、その変数の宣言で定義されている型です。</span><span class="sxs-lookup"><span data-stu-id="647d5-122">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="647d5-123">変数の "*実行時の型*" とは、その変数に代入されているインスタンスの型です。</span><span class="sxs-lookup"><span data-stu-id="647d5-123">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="647d5-124">*expr* が、*type* インターフェイスを実装する型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="647d5-124">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="647d5-125">C#7.1 以降、*expr* はジェネリック型パラメーターとその制約によって定義されるコンパイル時型を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="647d5-125">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="647d5-126">*expr* が `true` であり `is` が `if` ステートメントに使用されている場合は、*varname* は `if` ステートメント内のみに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="647d5-126">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="647d5-127">*varname* のスコープは、`is` 式から `if` ステートメントを閉じるブロックの末尾までになります。</span><span class="sxs-lookup"><span data-stu-id="647d5-127">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="647d5-128">他の任意の場所に *varname* を使用すると、割り当てられていない変数の使用によるコンパイル時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="647d5-128">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="647d5-129">次の例では、`is` 型のパターンを使用して、型 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> のメソッドの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="647d5-129">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="647d5-130">パターン マッチングを使用しない場合、このコードは次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="647d5-130">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="647d5-131">型パターン マッチングを使用することにより、変換結果が `null` であるかどうかをテストする必要がなくなるため、コードがよりコンパクトで読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="647d5-131">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="647d5-132">`is` 型パターンを使用すると、値の型の種類を判定する場合によりコンパクトなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="647d5-132">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="647d5-133">次の例では、`is` 型パターンを使用し、オブジェクトが `Person` インスタンスか `Dog` インスタンスかを判定した後に適切なプロパティの値を表示しています。</span><span class="sxs-lookup"><span data-stu-id="647d5-133">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="647d5-134">パターン マッチングを使用せずにこれと同等のコードを記述する場合は、明示的なキャストを含む代入処理を個別に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="647d5-134">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="647d5-135">定数パターン</span><span class="sxs-lookup"><span data-stu-id="647d5-135">Constant pattern</span></span>

<span data-ttu-id="647d5-136">定数パターンを使用してパターン マッチングを実行すると、式が指定された定数と等しいかどうかが `is` によってテストされます。</span><span class="sxs-lookup"><span data-stu-id="647d5-136">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="647d5-137">C# 6 以前のバージョンでの定数パターンは [switch](switch.md) ステートメントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="647d5-137">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="647d5-138">C# 7.0 以降では、`is` ステートメントでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="647d5-138">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="647d5-139">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="647d5-139">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="647d5-140">ここで *expr* は評価する式、*constant* はテストする値を表しています。</span><span class="sxs-lookup"><span data-stu-id="647d5-140">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="647d5-141">*constant* には、次のいずれかの定数式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="647d5-141">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="647d5-142">リテラル値。</span><span class="sxs-lookup"><span data-stu-id="647d5-142">A literal value.</span></span>

- <span data-ttu-id="647d5-143">宣言された `const` 変数の名前。</span><span class="sxs-lookup"><span data-stu-id="647d5-143">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="647d5-144">列挙定数。</span><span class="sxs-lookup"><span data-stu-id="647d5-144">An enumeration constant.</span></span>

<span data-ttu-id="647d5-145">定数式は以下のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="647d5-145">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="647d5-146">*expr* と *constant* が整数型の場合、式から `true` が返されるかどうか (つまり、`expr == constant` であるかどうか) が C# の等値演算子によって判定されます。</span><span class="sxs-lookup"><span data-stu-id="647d5-146">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="647d5-147">それ以外の場合、式の値は静的 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) メソッドの呼び出しによって判定されます。</span><span class="sxs-lookup"><span data-stu-id="647d5-147">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="647d5-148">次の例では、型パターンと定数パターンを組み合わせてオブジェクトが `Dice` インスタンスであるかどうかをテストし、そうである場合はサイコロ振り操作の値が 6 であるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="647d5-148">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="647d5-149">定数パターンを使用して、`null` のチェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="647d5-149">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="647d5-150">`is` ステートメントで `null` キーワードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="647d5-150">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="647d5-151">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="647d5-151">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="647d5-152">`null` チェックの比較を示す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="647d5-152">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="647d5-153">var パターン</span><span class="sxs-lookup"><span data-stu-id="647d5-153">var pattern</span></span>

<span data-ttu-id="647d5-154">`var` パターンによるパターン マッチは常に成功します。</span><span class="sxs-lookup"><span data-stu-id="647d5-154">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="647d5-155">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="647d5-155">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="647d5-156">ここで *expr* の値は常に *varname* というローカル変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="647d5-156">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="647d5-157">*varname* は、*expr* のコンパイル時の型と同じ型の変数です。</span><span class="sxs-lookup"><span data-stu-id="647d5-157">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="647d5-158">*expr* が `null` に評価された場合、`is` 式の結果 `true`が生成され、`null` が *varname* に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="647d5-158">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="647d5-159">var パターンは、`null` 値に対して `true` が生成される `is` の数少ない使用法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="647d5-159">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="647d5-160">次の例に示すように、`var` パターンを使用してブール式内に一時変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="647d5-160">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="647d5-161">前の例では、コストが高い操作の結果を格納するために一時変数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="647d5-161">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="647d5-162">変数は、複数回使用できます。</span><span class="sxs-lookup"><span data-stu-id="647d5-162">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="647d5-163">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="647d5-163">C# language specification</span></span>
  
<span data-ttu-id="647d5-164">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[The is operator (is 演算子)](~/_csharplang/spec/expressions.md#the-is-operator)」セクションおよび以下の C# 言語提案を参照してください。</span><span class="sxs-lookup"><span data-stu-id="647d5-164">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="647d5-165">パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="647d5-165">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="647d5-166">ジェネリックを使用したパターン マッチング</span><span class="sxs-lookup"><span data-stu-id="647d5-166">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="647d5-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="647d5-167">See also</span></span>

- [<span data-ttu-id="647d5-168">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="647d5-168">C# reference</span></span>](../index.md)
- [<span data-ttu-id="647d5-169">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="647d5-169">C# keywords</span></span>](index.md)
- [<span data-ttu-id="647d5-170">型テストとキャスト演算子</span><span class="sxs-lookup"><span data-stu-id="647d5-170">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
