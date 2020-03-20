---
title: is - C# リファレンス
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: e64b690482419963a92764b2c97a42dbb231fbfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398305"
---
# <a name="is-c-reference"></a><span data-ttu-id="5eede-102">is (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5eede-102">is (C# Reference)</span></span>

<span data-ttu-id="5eede-103">`is` 演算子では、式の結果と指定された型との間に互換性があるかどうかが確認されるか、または (C# 7.0 以降では) パターンに対して式がテストされます。</span><span class="sxs-lookup"><span data-stu-id="5eede-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="5eede-104">型テストの `is` 演算子について詳しくは、[型テストとキャスト演算子](../operators/type-testing-and-cast.md)に関する記事の「[is 演算子](../operators/type-testing-and-cast.md#is-operator)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5eede-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="5eede-105">`is` を使用したパターン マッチング</span><span class="sxs-lookup"><span data-stu-id="5eede-105">Pattern matching with `is`</span></span>

<span data-ttu-id="5eede-106">C# 7.0 以降では、`is` および [switch](switch.md) ステートメントでパターン マッチングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5eede-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="5eede-107">`is` キーワードでは、以下のパターンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5eede-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="5eede-108">[型パターン](#type-pattern)では、式を指定された型に変換できるかどうかがテストされ、変換できる場合はその型の変数にキャストされます。</span><span class="sxs-lookup"><span data-stu-id="5eede-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="5eede-109">[定数パターン](#constant-pattern): 式の評価が指定された定数値になるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="5eede-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="5eede-110">[var パターン](#var-pattern): 照合が常に成功し、式の値が新しいローカル変数にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="5eede-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="5eede-111">型パターン</span><span class="sxs-lookup"><span data-stu-id="5eede-111">Type pattern</span></span>

<span data-ttu-id="5eede-112">型パターンを使用してパターン マッチングを実行すると、式を指定された型に変換できるかどうかが `is` によってテストされ、変換できる場合はその型の変数にキャストされます。</span><span class="sxs-lookup"><span data-stu-id="5eede-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="5eede-113">`is` ステートメントのわかりやすい拡張機能であり、型の評価および変換を簡潔に記述できます。</span><span class="sxs-lookup"><span data-stu-id="5eede-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="5eede-114">`is` 型パターンの一般的な形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5eede-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="5eede-115">ここで *expr* は何らかの型のインスタンスに評価される式、*type* は *expr* の結果が変換される型の名前、*varname* は `is` のテスト結果が `true` である場合に *expr* の結果が変換されるオブジェクトをそれぞれ表しています。</span><span class="sxs-lookup"><span data-stu-id="5eede-115">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="5eede-116">*expr* が `null` ではなく、以下のいずれかの条件が true である場合に `is` 式は `true` となります。</span><span class="sxs-lookup"><span data-stu-id="5eede-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="5eede-117">*expr* が *type* と同じ型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="5eede-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="5eede-118">*expr* が *type* から派生した型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="5eede-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="5eede-119">つまり、*expr* の結果を *type* のインスタンスにアップキャストできる。</span><span class="sxs-lookup"><span data-stu-id="5eede-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="5eede-120">*expr* のコンパイル時の型が *type* の基底クラスであり、*expr* の実行時の型が *type* または *type* から派生した型である。</span><span class="sxs-lookup"><span data-stu-id="5eede-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="5eede-121">変数の "*コンパイル時の型*" とは、その変数の宣言で定義されている型です。</span><span class="sxs-lookup"><span data-stu-id="5eede-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="5eede-122">変数の "*実行時の型*" とは、その変数に代入されているインスタンスの型です。</span><span class="sxs-lookup"><span data-stu-id="5eede-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="5eede-123">*expr* が、*type* インターフェイスを実装する型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="5eede-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="5eede-124">C#7.1 以降、*expr* はジェネリック型パラメーターとその制約によって定義されるコンパイル時型を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="5eede-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="5eede-125">*expr* が `true` であり `is` が `if` ステートメントに使用されている場合は、*varname* は `if` ステートメント内のみに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5eede-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="5eede-126">*varname* のスコープは、`is` 式から `if` ステートメントを閉じるブロックの末尾までになります。</span><span class="sxs-lookup"><span data-stu-id="5eede-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="5eede-127">他の任意の場所に *varname* を使用すると、割り当てられていない変数の使用によるコンパイル時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5eede-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="5eede-128">次の例では、`is` 型のパターンを使用して、型 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> のメソッドの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="5eede-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="5eede-129">パターン マッチングを使用しない場合、このコードは次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="5eede-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="5eede-130">型パターン マッチングを使用することにより、変換結果が `null` であるかどうかをテストする必要がなくなるため、コードがよりコンパクトで読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="5eede-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="5eede-131">`is` 型パターンを使用すると、値の型の種類を判定する場合によりコンパクトなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="5eede-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="5eede-132">次の例では、`is` 型パターンを使用し、オブジェクトが `Person` インスタンスか `Dog` インスタンスかを判定した後に適切なプロパティの値を表示しています。</span><span class="sxs-lookup"><span data-stu-id="5eede-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="5eede-133">パターン マッチングを使用せずにこれと同等のコードを記述する場合は、明示的なキャストを含む代入処理を個別に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5eede-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="5eede-134">定数パターン</span><span class="sxs-lookup"><span data-stu-id="5eede-134">Constant pattern</span></span>

<span data-ttu-id="5eede-135">定数パターンを使用してパターン マッチングを実行すると、式が指定された定数と等しいかどうかが `is` によってテストされます。</span><span class="sxs-lookup"><span data-stu-id="5eede-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="5eede-136">C# 6 以前のバージョンでの定数パターンは [switch](switch.md) ステートメントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5eede-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="5eede-137">C# 7.0 以降では、`is` ステートメントでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5eede-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="5eede-138">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5eede-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="5eede-139">ここで *expr* は評価する式、*constant* はテストする値を表しています。</span><span class="sxs-lookup"><span data-stu-id="5eede-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="5eede-140">*constant* には以下のいずれかの定数式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5eede-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="5eede-141">リテラル値。</span><span class="sxs-lookup"><span data-stu-id="5eede-141">A literal value.</span></span>

- <span data-ttu-id="5eede-142">宣言された `const` 変数の名前。</span><span class="sxs-lookup"><span data-stu-id="5eede-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="5eede-143">列挙定数。</span><span class="sxs-lookup"><span data-stu-id="5eede-143">An enumeration constant.</span></span>

<span data-ttu-id="5eede-144">定数式は以下のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="5eede-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="5eede-145">*expr* と *constant* が整数型の場合、式から `true` が返されるかどうか (つまり、`expr == constant` であるかどうか) が C# の等値演算子によって判定されます。</span><span class="sxs-lookup"><span data-stu-id="5eede-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="5eede-146">それ以外の場合、式の値は静的 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) メソッドの呼び出しによって判定されます。</span><span class="sxs-lookup"><span data-stu-id="5eede-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="5eede-147">次の例では、型パターンと定数パターンを組み合わせてオブジェクトが `Dice` インスタンスであるかどうかをテストし、そうである場合はサイコロ振り操作の値が 6 であるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="5eede-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="5eede-148">定数パターンを使用して、`null` のチェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5eede-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="5eede-149">`is` ステートメントで `null` キーワードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5eede-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="5eede-150">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5eede-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="5eede-151">`null` チェックの比較を示す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5eede-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="5eede-152">var パターン</span><span class="sxs-lookup"><span data-stu-id="5eede-152">var pattern</span></span>

<span data-ttu-id="5eede-153">`var` パターンによるパターン マッチは常に成功します。</span><span class="sxs-lookup"><span data-stu-id="5eede-153">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="5eede-154">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5eede-154">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="5eede-155">ここで *expr* の値は常に *varname* というローカル変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="5eede-155">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="5eede-156">*varname* は、*expr* のコンパイル時の型と同じ型の変数です。</span><span class="sxs-lookup"><span data-stu-id="5eede-156">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="5eede-157">*expr* が `null` に評価された場合、`is` 式の結果 `true`が生成され、`null` が *varname* に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5eede-157">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="5eede-158">var パターンは、`null` 値に対して `true` が生成される `is` の数少ない使用法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="5eede-158">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="5eede-159">次の例に示すように、`var` パターンを使用してブール式内に一時変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5eede-159">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="5eede-160">前の例では、コストが高い操作の結果を格納するために一時変数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="5eede-160">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="5eede-161">変数は、複数回使用できます。</span><span class="sxs-lookup"><span data-stu-id="5eede-161">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5eede-162">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5eede-162">C# language specification</span></span>
  
<span data-ttu-id="5eede-163">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[The is operator (is 演算子)](~/_csharplang/spec/expressions.md#the-is-operator)」セクションおよび以下の C# 言語提案を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5eede-163">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="5eede-164">パターン マッチング</span><span class="sxs-lookup"><span data-stu-id="5eede-164">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="5eede-165">ジェネリックを使用したパターン マッチング</span><span class="sxs-lookup"><span data-stu-id="5eede-165">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="5eede-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="5eede-166">See also</span></span>

- [<span data-ttu-id="5eede-167">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="5eede-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5eede-168">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="5eede-168">C# keywords</span></span>](index.md)
- [<span data-ttu-id="5eede-169">型テストとキャスト演算子</span><span class="sxs-lookup"><span data-stu-id="5eede-169">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
