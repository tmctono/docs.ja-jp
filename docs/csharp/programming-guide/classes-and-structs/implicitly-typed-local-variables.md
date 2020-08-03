---
title: 暗黙的に型指定されるローカル変数 - C# プログラミング ガイド
description: C# の var キーワードは、初期化ステートメントの右辺にある式から変数の型を推論するようにコンパイラに指示します。
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 6badb8588dedda80227ab38bee027cf2890c8672
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864216"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="18ddb-103">暗黙的に型指定されるローカル変数 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="18ddb-103">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="18ddb-104">ローカル変数は、明示的な型を指定しないで宣言できます。</span><span class="sxs-lookup"><span data-stu-id="18ddb-104">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="18ddb-105">`var` キーワードは、初期化ステートメントの右辺にある式から変数の型を推論するようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="18ddb-105">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="18ddb-106">推論される型は、組み込み型、匿名型、ユーザー定義型、または .NET クラス ライブラリで定義されている型である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18ddb-106">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET class library.</span></span> <span data-ttu-id="18ddb-107">`var` で配列を初期化する方法の詳細については、「[暗黙的に型指定される配列](../arrays/implicitly-typed-arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18ddb-107">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="18ddb-108">ローカル変数を `var` で宣言するさまざまな方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="18ddb-108">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="18ddb-109">`var` キーワードは "バリアント" を意味するのではなく、変数の厳密でない型指定や遅延バインディングを示すものでもないことを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="18ddb-109">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="18ddb-110">単に、最も適切な型をコンパイラが決定して割り当てることを意味します。</span><span class="sxs-lookup"><span data-stu-id="18ddb-110">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="18ddb-111">`var` キーワードは、次のコンテキストで使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="18ddb-111">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="18ddb-112">前の例で示したようなローカル変数 (メソッドのスコープで宣言された変数)。</span><span class="sxs-lookup"><span data-stu-id="18ddb-112">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="18ddb-113">[for](../../language-reference/keywords/for.md) 初期化ステートメント。</span><span class="sxs-lookup"><span data-stu-id="18ddb-113">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for (var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="18ddb-114">[foreach](../../language-reference/keywords/foreach-in.md) 初期化ステートメント。</span><span class="sxs-lookup"><span data-stu-id="18ddb-114">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach (var item in list) {...}
    ```

- <span data-ttu-id="18ddb-115">[using](../../language-reference/keywords/using-statement.md) ステートメント。</span><span class="sxs-lookup"><span data-stu-id="18ddb-115">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="18ddb-116">詳細については、「[「クエリ式で暗黙的に型指定されるローカル変数および配列を使用する方法](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18ddb-116">For more information, see [How to use implicitly typed local variables and arrays in a query expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="18ddb-117">var と匿名型</span><span class="sxs-lookup"><span data-stu-id="18ddb-117">var and anonymous types</span></span>

<span data-ttu-id="18ddb-118">多くの場合、`var` の使用は任意であり、構文上便利なだけです。</span><span class="sxs-lookup"><span data-stu-id="18ddb-118">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="18ddb-119">ただし、変数が匿名型で初期化される場合、後でオブジェクトのプロパティへのアクセスが必要になったら、変数を `var` として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18ddb-119">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="18ddb-120">これは、LINQ クエリ式では一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="18ddb-120">This is a common scenario in LINQ query expressions.</span></span> <span data-ttu-id="18ddb-121">詳細については、「[匿名型](anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18ddb-121">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="18ddb-122">ソース コードの観点から見ると、匿名型には名前がありません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-122">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="18ddb-123">そのため、クエリ変数が `var` で初期化された場合、返されたオブジェクトのシーケンスのプロパティにアクセスするための唯一の方法は、`foreach` ステートメント内の繰り返し変数の型として `var` を使用することです。</span><span class="sxs-lookup"><span data-stu-id="18ddb-123">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="18ddb-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="18ddb-124">Remarks</span></span>

<span data-ttu-id="18ddb-125">暗黙的に型指定される変数の宣言には、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="18ddb-125">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="18ddb-126">`var` を使用できるのは、同じステートメント内でローカル変数の宣言と初期化が行われる場合のみです。この変数は、null、メソッド グループ、または匿名関数に初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-126">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="18ddb-127">`var` は、クラス スコープのフィールドで使用できません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-127">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="18ddb-128">`var` を使用して宣言された変数は、初期化式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-128">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="18ddb-129">つまり、`int i = (i = 20);` という式は有効ですが、`var i = (i = 20);` という式はコンパイル時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="18ddb-129">In other words, this expression is legal: `int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="18ddb-130">暗黙的に型指定された複数の変数を同じステートメント内で初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-130">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="18ddb-131">`var` という名前の型がスコープ内にある場合、`var` キーワードはその型名に解決され、暗黙的に型指定されたローカル変数の宣言の一部とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-131">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="18ddb-132">`var` キーワードによる暗黙の型指定は、ローカル メソッド スコープの変数にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="18ddb-132">Implicit typing with the `var` keyword can only be applied to variables at local method scope.</span></span> <span data-ttu-id="18ddb-133">暗黙の型指定はクラス フィールドには使用できません。C# コンパイラでコードを処理するときに論理的パラドックスにぶつかるためです。コンパイラはフィールドの型を認識する必要がありますが、代入式が分析されるまで型を判断できません。そして、型を認識していなければ、式を評価できません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-133">Implicit typing is not available for class fields as the C# compiler would encounter a logical paradox as it processed the code: the compiler needs to know the type of the field, but it cannot determine the type until the assignment expression is analyzed, and the expression cannot be evaluated without knowing the type.</span></span> <span data-ttu-id="18ddb-134">次のコードがあるとします。</span><span class="sxs-lookup"><span data-stu-id="18ddb-134">Consider the following code:</span></span>

```csharp
private var bookTitles;
```

<span data-ttu-id="18ddb-135">`bookTitles` は、型が `var` のクラス フィールドです。</span><span class="sxs-lookup"><span data-stu-id="18ddb-135">`bookTitles` is a class field given the type `var`.</span></span> <span data-ttu-id="18ddb-136">このフィールドには評価する式がないため、コンパイラでは `bookTitles` の型を推定できません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-136">As the field has no expression to evaluate, it is impossible for the compiler to infer what type `bookTitles` is supposed to be.</span></span> <span data-ttu-id="18ddb-137">さらに、(ローカル変数の場合と同様に) フィールドに式を追加するだけでは不十分です。</span><span class="sxs-lookup"><span data-stu-id="18ddb-137">In addition, adding an expression to the field (like you would for a local variable) is also insufficient:</span></span>

```csharp
private var bookTitles = new List<string>();
```

<span data-ttu-id="18ddb-138">コードのコンパイル中にコンパイラでフィールドが検出されると、それに関連付けられている式を処理する前に各フィールドの型が記録されます。</span><span class="sxs-lookup"><span data-stu-id="18ddb-138">When the compiler encounters fields during code compilation, it records each field's type before processing any expressions associated with it.</span></span> <span data-ttu-id="18ddb-139">コンパイラでの `bookTitles` の解析時に同じパラドックスにぶつかります。フィールドの型を認識する必要がありますが、通常、コンパイラは式を解析して `var` の型を判断します。これには、事前に型を認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="18ddb-139">The compiler encounters the same paradox trying to parse `bookTitles`: it needs to know the type of the field, but the compiler would normally determine `var`'s type by analyzing the expression, which isn't possible without knowing the type beforehand.</span></span>

<span data-ttu-id="18ddb-140">`var` は、クエリ式と使用する場合に便利なこともあります。クエリ変数の構築された型を厳密に判別することが難しい場合です。</span><span class="sxs-lookup"><span data-stu-id="18ddb-140">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="18ddb-141">このような状況は、グループ化と並べ替えの処理で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="18ddb-141">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="18ddb-142">`var` キーワードは、変数の特定の型をキーボードで入力するのが面倒な場合、その型が明白な場合、型によってコードが読みやすくならない場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="18ddb-142">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="18ddb-143">このような理由で `var` が有用な例の 1 つとして、グループ化処理で使用されるような入れ子にされたジェネリック型があります。</span><span class="sxs-lookup"><span data-stu-id="18ddb-143">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="18ddb-144">次のクエリでは、クエリ変数の型は `IEnumerable<IGrouping<string, Student>>` です。</span><span class="sxs-lookup"><span data-stu-id="18ddb-144">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="18ddb-145">コードの作成者とそのコードを保守する担当者がこの点を理解している限り、簡略化するために暗黙的な型指定を使用しても問題はありません。</span><span class="sxs-lookup"><span data-stu-id="18ddb-145">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="18ddb-146">`var` を使用すると、コードを簡単にすることができますが、必要な場合、またはコードを読みやすくする場合にのみ使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="18ddb-146">The use of `var` helps simplify your code, but its use should be restricted to cases where it is required, or when it makes your code easier to read.</span></span> <span data-ttu-id="18ddb-147">`var` 使用するのが適切な場合の詳細については、C# コーディング ガイドラインの記事の「[暗黙的に型指定されるローカル変数](../inside-a-program/coding-conventions.md#implicitly-typed-local-variables)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18ddb-147">For more information about when to use `var` properly, see the [Implicitly typed local variables](../inside-a-program/coding-conventions.md#implicitly-typed-local-variables) section on the C# Coding Guidelines article.</span></span>

## <a name="see-also"></a><span data-ttu-id="18ddb-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="18ddb-148">See also</span></span>

- [<span data-ttu-id="18ddb-149">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="18ddb-149">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="18ddb-150">暗黙的に型指定される配列</span><span class="sxs-lookup"><span data-stu-id="18ddb-150">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="18ddb-151">クエリ式で暗黙的に型指定されるローカル変数および配列を使用する方法</span><span class="sxs-lookup"><span data-stu-id="18ddb-151">How to use implicitly typed local variables and arrays in a query expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="18ddb-152">匿名型</span><span class="sxs-lookup"><span data-stu-id="18ddb-152">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="18ddb-153">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="18ddb-153">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="18ddb-154">var</span><span class="sxs-lookup"><span data-stu-id="18ddb-154">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="18ddb-155">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="18ddb-155">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="18ddb-156">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="18ddb-156">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="18ddb-157">for</span><span class="sxs-lookup"><span data-stu-id="18ddb-157">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="18ddb-158">foreach、in</span><span class="sxs-lookup"><span data-stu-id="18ddb-158">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="18ddb-159">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="18ddb-159">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
