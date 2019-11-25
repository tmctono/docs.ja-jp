---
title: 暗黙的に型指定されるローカル変数 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: dab708bfbc33458bc2664c0d04757f0badcc2575
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141608"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="3faf2-102">暗黙的に型指定されるローカル変数 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="3faf2-102">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="3faf2-103">ローカル変数は、明示的な型を指定しないで宣言できます。</span><span class="sxs-lookup"><span data-stu-id="3faf2-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="3faf2-104">`var` キーワードは、初期化ステートメントの右辺にある式から変数の型を推論するようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="3faf2-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="3faf2-105">推論される型は、組み込み型、匿名型、ユーザー定義型、または .NET Framework クラス ライブラリで定義されている型である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3faf2-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="3faf2-106">`var` で配列を初期化する方法の詳細については、「[暗黙的に型指定される配列](../arrays/implicitly-typed-arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3faf2-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="3faf2-107">ローカル変数を `var` で宣言するさまざまな方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="3faf2-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="3faf2-108">`var` キーワードは "バリアント" を意味するのではなく、変数の厳密でない型指定や遅延バインディングを示すものでもないことを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3faf2-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="3faf2-109">単に、最も適切な型をコンパイラが決定して割り当てることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3faf2-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="3faf2-110">`var` キーワードは、次のコンテキストで使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3faf2-110">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="3faf2-111">前の例で示したようなローカル変数 (メソッドのスコープで宣言された変数)。</span><span class="sxs-lookup"><span data-stu-id="3faf2-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="3faf2-112">[for](../../language-reference/keywords/for.md) 初期化ステートメント。</span><span class="sxs-lookup"><span data-stu-id="3faf2-112">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for (var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="3faf2-113">[foreach](../../language-reference/keywords/foreach-in.md) 初期化ステートメント。</span><span class="sxs-lookup"><span data-stu-id="3faf2-113">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach (var item in list) {...}
    ```

- <span data-ttu-id="3faf2-114">[using](../../language-reference/keywords/using-statement.md) ステートメント。</span><span class="sxs-lookup"><span data-stu-id="3faf2-114">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="3faf2-115">詳細については、「[「クエリ式で暗黙的に型指定されるローカル変数および配列を使用する方法](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3faf2-115">For more information, see [How to use implicitly typed local variables and arrays in a query expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="3faf2-116">var と匿名型</span><span class="sxs-lookup"><span data-stu-id="3faf2-116">var and anonymous types</span></span>

<span data-ttu-id="3faf2-117">多くの場合、`var` の使用は任意であり、構文上便利なだけです。</span><span class="sxs-lookup"><span data-stu-id="3faf2-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="3faf2-118">ただし、変数が匿名型で初期化される場合、後でオブジェクトのプロパティへのアクセスが必要になったら、変数を `var` として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3faf2-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="3faf2-119">これは、[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] クエリ式では一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="3faf2-119">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="3faf2-120">詳細については、「[匿名型](anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3faf2-120">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="3faf2-121">ソース コードの観点から見ると、匿名型には名前がありません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="3faf2-122">そのため、クエリ変数が `var` で初期化された場合、返されたオブジェクトのシーケンスのプロパティにアクセスするための唯一の方法は、`foreach` ステートメント内の繰り返し変数の型として `var` を使用することです。</span><span class="sxs-lookup"><span data-stu-id="3faf2-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="3faf2-123">解説</span><span class="sxs-lookup"><span data-stu-id="3faf2-123">Remarks</span></span>

<span data-ttu-id="3faf2-124">暗黙的に型指定される変数の宣言には、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3faf2-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="3faf2-125">`var` を使用できるのは、同じステートメント内でローカル変数の宣言と初期化が行われる場合のみです。この変数は、null、メソッド グループ、または匿名関数に初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="3faf2-126">`var` は、クラス スコープのフィールドで使用できません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-126">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="3faf2-127">`var` を使用して宣言された変数は、初期化式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="3faf2-128">つまり、`int i = (i = 20);` という式は有効ですが、`var i = (i = 20);` という式はコンパイル時エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3faf2-128">In other words, this expression is legal: `int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="3faf2-129">暗黙的に型指定された複数の変数を同じステートメント内で初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="3faf2-130">`var` という名前の型がスコープ内にある場合、`var` キーワードはその型名に解決され、暗黙的に型指定されたローカル変数の宣言の一部とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="3faf2-131">`var` キーワードによる暗黙の型指定は、ローカル メソッド スコープの変数にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="3faf2-131">Implicit typing with the `var` keyword can only be applied to variables at local method scope.</span></span> <span data-ttu-id="3faf2-132">暗黙の型指定はクラス フィールドには使用できません。C# コンパイラでコードを処理するときに論理的パラドックスにぶつかるためです。コンパイラはフィールドの型を認識する必要がありますが、代入式が分析されるまで型を判断できません。そして、型を認識していなければ、式を評価できません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-132">Implicit typing is not available for class fields as the C# compiler would encounter a logical paradox as it processed the code: the compiler needs to know the type of the field, but it cannot determine the type until the assignment expression is analyzed, and the expression cannot be evaluated without knowing the type.</span></span> <span data-ttu-id="3faf2-133">次のコードがあるとします。</span><span class="sxs-lookup"><span data-stu-id="3faf2-133">Consider the following code:</span></span>

```csharp
private var bookTitles;
```

<span data-ttu-id="3faf2-134">`bookTitles` は、型が `var` のクラス フィールドです。</span><span class="sxs-lookup"><span data-stu-id="3faf2-134">`bookTitles` is a class field given the type `var`.</span></span> <span data-ttu-id="3faf2-135">このフィールドには評価する式がないため、コンパイラでは `bookTitles` の型を推定できません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-135">As the field has no expression to evaluate, it is impossible for the compiler to infer what type `bookTitles` is supposed to be.</span></span> <span data-ttu-id="3faf2-136">さらに、(ローカル変数の場合と同様に) フィールドに式を追加するだけでは不十分です。</span><span class="sxs-lookup"><span data-stu-id="3faf2-136">In addition, adding an expression to the field (like you would for a local variable) is also insufficient:</span></span>

```csharp
private var bookTitles = new List<string>();
```

<span data-ttu-id="3faf2-137">コードのコンパイル中にコンパイラでフィールドが検出されると、それに関連付けられている式を処理する前に各フィールドの型が記録されます。</span><span class="sxs-lookup"><span data-stu-id="3faf2-137">When the compiler encounters fields during code compilation, it records each field's type before processing any expressions associated with it.</span></span> <span data-ttu-id="3faf2-138">コンパイラでの `bookTitles` の解析時に同じパラドックスにぶつかります。フィールドの型を認識する必要がありますが、通常、コンパイラは式を解析して `var` の型を判断します。これには、事前に型を認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3faf2-138">The compiler encounters the same paradox trying to parse `bookTitles`: it needs to know the type of the field, but the compiler would normally determine `var`'s type by analyzing the expression, which isn't possible without knowing the type beforehand.</span></span>

<span data-ttu-id="3faf2-139">`var` は、クエリ式と使用する場合に便利なこともあります。クエリ変数の構築された型を厳密に判別することが難しい場合です。</span><span class="sxs-lookup"><span data-stu-id="3faf2-139">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="3faf2-140">このような状況は、グループ化と並べ替えの処理で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="3faf2-140">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="3faf2-141">`var` キーワードは、変数の特定の型をキーボードで入力するのが面倒な場合、その型が明白な場合、型によってコードが読みやすくならない場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3faf2-141">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="3faf2-142">このような理由で `var` が有用な例の 1 つとして、グループ化処理で使用されるような入れ子にされたジェネリック型があります。</span><span class="sxs-lookup"><span data-stu-id="3faf2-142">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="3faf2-143">次のクエリでは、クエリ変数の型は `IEnumerable<IGrouping<string, Student>>` です。</span><span class="sxs-lookup"><span data-stu-id="3faf2-143">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="3faf2-144">コードの作成者とそのコードを保守する担当者がこの点を理解している限り、簡略化するために暗黙的な型指定を使用しても問題はありません。</span><span class="sxs-lookup"><span data-stu-id="3faf2-144">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="3faf2-145">ただし、`var` を使用すると、他の開発者がコードを理解しづらくなる可能性はあります。</span><span class="sxs-lookup"><span data-stu-id="3faf2-145">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="3faf2-146">このため、C# のドキュメントでは、通常、必要な場合にだけ `var` を使用しています。</span><span class="sxs-lookup"><span data-stu-id="3faf2-146">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>

## <a name="see-also"></a><span data-ttu-id="3faf2-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="3faf2-147">See also</span></span>

- [<span data-ttu-id="3faf2-148">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3faf2-148">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="3faf2-149">暗黙的に型指定される配列</span><span class="sxs-lookup"><span data-stu-id="3faf2-149">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="3faf2-150">クエリ式で暗黙的に型指定されるローカル変数および配列を使用する方法</span><span class="sxs-lookup"><span data-stu-id="3faf2-150">How to use implicitly typed local variables and arrays in a query expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="3faf2-151">匿名型</span><span class="sxs-lookup"><span data-stu-id="3faf2-151">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="3faf2-152">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="3faf2-152">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="3faf2-153">var</span><span class="sxs-lookup"><span data-stu-id="3faf2-153">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="3faf2-154">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="3faf2-154">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="3faf2-155">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="3faf2-155">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="3faf2-156">for</span><span class="sxs-lookup"><span data-stu-id="3faf2-156">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="3faf2-157">foreach、in</span><span class="sxs-lookup"><span data-stu-id="3faf2-157">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="3faf2-158">using ステートメント</span><span class="sxs-lookup"><span data-stu-id="3faf2-158">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
