---
title: is - C# リファレンス
ms.custom: seodec18
ms.date: 04/09/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 83cb308a14a6db99f65b30eded20442d675cbd57
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480834"
---
# <a name="is-c-reference"></a><span data-ttu-id="af259-102">is (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="af259-102">is (C# Reference)</span></span>

<span data-ttu-id="af259-103">オブジェクトに指定された型との互換性があるかどうかを確認するか、(C# 7.0 以降では) パターンとの比較によって式をテストします。</span><span class="sxs-lookup"><span data-stu-id="af259-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="af259-104">型の互換性に関するテスト</span><span class="sxs-lookup"><span data-stu-id="af259-104">Testing for type compatibility</span></span>

<span data-ttu-id="af259-105">`is` キーワードを使用すると、実行時に型の互換性が評価されます。</span><span class="sxs-lookup"><span data-stu-id="af259-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="af259-106">これにより、オブジェクト インスタンスや式の結果を指定された型に変換できるかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="af259-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="af259-107">構文は次のとおりです</span><span class="sxs-lookup"><span data-stu-id="af259-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="af259-108">ここで *expr* は何らかの型のインスタンスに評価される式、*type* は *expr* の結果が変換される型の名前です。</span><span class="sxs-lookup"><span data-stu-id="af259-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="af259-109">`is` ステートメントでは、*expr* が null 以外の値で、式の評価によって得られるオブジェクトが *type* に変換できる場合に `true`、それ以外の場合に `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="af259-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="af259-110">たとえば、次のコードでは `obj` を `Person` 型のインスタンスにキャストできるかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="af259-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="af259-111">`is` ステートメントは以下の場合に true となります。</span><span class="sxs-lookup"><span data-stu-id="af259-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="af259-112">*expr* が *type* と同じ型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="af259-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="af259-113">*expr* が *type* から派生した型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="af259-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="af259-114">つまり、*expr* の結果を *type* のインスタンスにアップキャストできる。</span><span class="sxs-lookup"><span data-stu-id="af259-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="af259-115">*expr* のコンパイル時の型が *type* の基底クラスであり、*expr* の実行時の型が *type* または *type* から派生した型である。</span><span class="sxs-lookup"><span data-stu-id="af259-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="af259-116">変数の "*コンパイル時の型*" とは、その変数の宣言で定義されている型です。</span><span class="sxs-lookup"><span data-stu-id="af259-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="af259-117">変数の "*実行時の型*" とは、その変数に代入されているインスタンスの型です。</span><span class="sxs-lookup"><span data-stu-id="af259-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="af259-118">*expr* が、*type* インターフェイスを実装する型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="af259-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="af259-119">次の例は、変換ごとの `is` 式の評価が `true` となることを示しています。</span><span class="sxs-lookup"><span data-stu-id="af259-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="af259-120">式が常に `true` または `false` のいずれかになることが判明している場合は、`is` キーワードによってコンパイル時に警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="af259-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="af259-121">参照変換、ボックス変換、アンボックス変換のみが考慮され、ユーザー定義の変換や型の [implicit](implicit.md) および [explicit](explicit.md) 演算子によって定義された変換は無視されます。</span><span class="sxs-lookup"><span data-stu-id="af259-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="af259-122">次の例では、コンパイル時に変換結果が判明しているため、警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="af259-122">The following example generates warnings because the result of the conversion is known at compile time.</span></span> <span data-ttu-id="af259-123">`int` から `long` および `double` への変換の `is` 式では、変換が [implicit](implicit.md) 演算子によって処理されるため、false が返されます。</span><span class="sxs-lookup"><span data-stu-id="af259-123">The `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

`expr` <span data-ttu-id="af259-124">匿名メソッドまたはラムダ式にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="af259-124">cannot be an anonymous method or lambda expression.</span></span> <span data-ttu-id="af259-125">値を返す他の式を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="af259-125">It can be any other expression that returns a value.</span></span> <span data-ttu-id="af259-126">次の例では、`is` を使用してメソッド呼び出しの戻り値を評価しています。</span><span class="sxs-lookup"><span data-stu-id="af259-126">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="af259-127">C# 7.0 以降では、[型パターン](#type)によるパターン マッチングを使用することで、`is` ステートメントを用いたより簡潔なコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="af259-127">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="af259-128">`is` を使用したパターン マッチング</span><span class="sxs-lookup"><span data-stu-id="af259-128">Pattern matching with `is`</span></span>

<span data-ttu-id="af259-129">C# 7.0 以降では、`is` および [switch](../../../csharp/language-reference/keywords/switch.md) ステートメントでパターン マッチングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af259-129">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="af259-130">`is` キーワードでは、以下のパターンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af259-130">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="af259-131">[型パターン](#type): 式を指定された型に変換できるかどうかをテストし、変換できる場合はその型の変数にキャストします。</span><span class="sxs-lookup"><span data-stu-id="af259-131">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="af259-132">[定数パターン](#constant): 式の評価が指定された定数値になるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="af259-132">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="af259-133">[var パターン](#var): 照合が常に成功し、式の値が新しいローカル変数にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="af259-133">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <a name="a-nametype-type-pattern"></a><span data-ttu-id="af259-134"><a name="type" />型パターン</span><span class="sxs-lookup"><span data-stu-id="af259-134"><a name="type" />Type pattern</span></span>

<span data-ttu-id="af259-135">型パターンを使用してパターン マッチングを実行すると、式を指定された型に変換できるかどうかが `is` によってテストされ、変換できる場合はその型の変数にキャストされます。</span><span class="sxs-lookup"><span data-stu-id="af259-135">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="af259-136">`is` ステートメントのわかりやすい拡張機能であり、型の評価および変換を簡潔に記述できます。</span><span class="sxs-lookup"><span data-stu-id="af259-136">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="af259-137">`is` 型パターンの一般的な形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af259-137">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="af259-138">ここで *expr* は何らかの型のインスタンスに評価される式、*type* は *expr* の結果が変換される型の名前、*varname* は `is` のテスト結果が `true` である場合に *expr* の結果が変換されるオブジェクトをそれぞれ表しています。</span><span class="sxs-lookup"><span data-stu-id="af259-138">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="af259-139">*expr* が `null` ではなく、以下のいずれかの条件が true である場合に `is` 式は `true` となります。</span><span class="sxs-lookup"><span data-stu-id="af259-139">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="af259-140">*expr* が *type* と同じ型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="af259-140">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="af259-141">*expr* が *type* から派生した型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="af259-141">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="af259-142">つまり、*expr* の結果を *type* のインスタンスにアップキャストできる。</span><span class="sxs-lookup"><span data-stu-id="af259-142">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="af259-143">*expr* のコンパイル時の型が *type* の基底クラスであり、*expr* の実行時の型が *type* または *type* から派生した型である。</span><span class="sxs-lookup"><span data-stu-id="af259-143">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="af259-144">変数の "*コンパイル時の型*" とは、その変数の宣言で定義されている型です。</span><span class="sxs-lookup"><span data-stu-id="af259-144">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="af259-145">変数の "*実行時の型*" とは、その変数に代入されているインスタンスの型です。</span><span class="sxs-lookup"><span data-stu-id="af259-145">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="af259-146">*expr* が、*type* インターフェイスを実装する型のインスタンスである。</span><span class="sxs-lookup"><span data-stu-id="af259-146">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="af259-147">C#7.1 以降、*expr* はジェネリック型パラメーターとその制約によって定義されるコンパイル時型を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="af259-147">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span> 

<span data-ttu-id="af259-148">*expr* が `true` で `is` が `if` ステートメントと共に使用されている場合は *varname* への代入が行われ、そのローカル スコープは `if` ステートメント内に限定されます。</span><span class="sxs-lookup"><span data-stu-id="af259-148">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="af259-149">次の例では、`is` 型のパターンを使用して、型 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> のメソッドの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="af259-149">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="af259-150">パターン マッチングを使用しない場合、このコードは次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="af259-150">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="af259-151">型パターン マッチングを使用することにより、変換結果が `null` であるかどうかをテストする必要がなくなるため、コードがよりコンパクトで読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="af259-151">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="af259-152">`is` 型パターンを使用すると、値の型の種類を判定する場合によりコンパクトなコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="af259-152">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="af259-153">次の例では、`is` 型パターンを使用し、オブジェクトが `Person` インスタンスか `Dog` インスタンスかを判定した後に適切なプロパティの値を表示しています。</span><span class="sxs-lookup"><span data-stu-id="af259-153">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="af259-154">パターン マッチングを使用せずにこれと同等のコードを記述する場合は、明示的なキャストを含む代入処理を個別に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="af259-154">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="af259-155"><a name="constant" />定数パターン</span><span class="sxs-lookup"><span data-stu-id="af259-155"><a name="constant" /> Constant pattern</span></span>

<span data-ttu-id="af259-156">定数パターンを使用してパターン マッチングを実行すると、式が指定された定数と等しいかどうかが `is` によってテストされます。</span><span class="sxs-lookup"><span data-stu-id="af259-156">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="af259-157">C# 6 以前のバージョンでの定数パターンは [switch](switch.md) ステートメントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af259-157">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="af259-158">C# 7.0 以降では、`is` ステートメントでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af259-158">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="af259-159">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af259-159">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="af259-160">ここで *expr* は評価する式、*constant* はテストする値を表しています。</span><span class="sxs-lookup"><span data-stu-id="af259-160">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="af259-161">*constant* には以下のいずれかの定数式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="af259-161">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="af259-162">リテラル値。</span><span class="sxs-lookup"><span data-stu-id="af259-162">A literal value.</span></span>

- <span data-ttu-id="af259-163">宣言された `const` 変数の名前。</span><span class="sxs-lookup"><span data-stu-id="af259-163">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="af259-164">列挙定数。</span><span class="sxs-lookup"><span data-stu-id="af259-164">An enumeration constant.</span></span>

<span data-ttu-id="af259-165">定数式は以下のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="af259-165">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="af259-166">*expr* と *constant* が整数型の場合、式から `true` が返されるかどうか (つまり、`expr == constant` であるかどうか) が C# の等値演算子によって判定されます。</span><span class="sxs-lookup"><span data-stu-id="af259-166">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="af259-167">それ以外の場合、式の値は静的 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) メソッドの呼び出しによって判定されます。</span><span class="sxs-lookup"><span data-stu-id="af259-167">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="af259-168">次の例では、型パターンと定数パターンを組み合わせてオブジェクトが `Dice` インスタンスであるかどうかをテストし、そうである場合はサイコロ振り操作の値が 6 であるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="af259-168">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="af259-169">定数パターンを使用して、`null` のチェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="af259-169">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="af259-170">`is` ステートメントで `null` キーワードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af259-170">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="af259-171">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af259-171">Its syntax is:</span></span>

```csharp 
   expr is null
```

<span data-ttu-id="af259-172">`null` チェックの比較を示す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="af259-172">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <span data-ttu-id="af259-173"><a name="var" /> var パターン</a></span><span class="sxs-lookup"><span data-stu-id="af259-173"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="af259-174">var パターンとのパターン マッチは、常に null 以外の式に対して成功します。*expr* が `null` の場合、`is` 式は `false` です。</span><span class="sxs-lookup"><span data-stu-id="af259-174">A pattern match with the var pattern always succeeds for non-null expressions; if *expr* is `null`, the `is` expression is `false`.</span></span> <span data-ttu-id="af259-175">*expr* の null 以外の値は、常に *expr* の実行時の型と同じ型のローカル変数に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="af259-175">The non-null value of *expr* is always assigned to a local variable the same type as the runtime time type of *expr*.</span></span>  <span data-ttu-id="af259-176">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af259-176">Its syntax is:</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="af259-177">次の例では、var パターンを使用して式を `obj` という変数に代入しています。</span><span class="sxs-lookup"><span data-stu-id="af259-177">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="af259-178">その後、`obj` の値と型が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af259-178">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="af259-179">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="af259-179">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="af259-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="af259-180">See also</span></span>

- [<span data-ttu-id="af259-181">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="af259-181">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="af259-182">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="af259-182">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="af259-183">typeof</span><span class="sxs-lookup"><span data-stu-id="af259-183">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
- [<span data-ttu-id="af259-184">as</span><span class="sxs-lookup"><span data-stu-id="af259-184">as</span></span>](../../../csharp/language-reference/keywords/as.md)
- [<span data-ttu-id="af259-185">演算子のキーワード</span><span class="sxs-lookup"><span data-stu-id="af259-185">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
