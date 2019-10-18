---
title: クエリ操作での型の関係 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: 6d5d13064cceba10d27901ee95aa8b6731620dbb
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524118"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="81022-102">クエリ操作での型の関係 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81022-102">Type Relationships in Query Operations (Visual Basic)</span></span>

<span data-ttu-id="81022-103">@No__t_0 クエリ操作で使用される変数は厳密に型指定され、相互に互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="81022-103">Variables used in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="81022-104">厳密な型指定は、データソース、クエリ自体、およびクエリの実行で使用されます。</span><span class="sxs-lookup"><span data-stu-id="81022-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="81022-105">次の図は、[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] クエリを記述するために使用される用語を示しています。</span><span class="sxs-lookup"><span data-stu-id="81022-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="81022-106">クエリの各部分の詳細については、「[クエリの基本操作 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81022-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>

![要素が強調表示されている擬似コードクエリを示すスクリーンショット。](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

<span data-ttu-id="81022-108">クエリ内の範囲変数の型は、データソース内の要素の型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="81022-108">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="81022-109">クエリ変数の型は、`Select` 句で定義されている sequence 要素と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="81022-109">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="81022-110">最後に、シーケンス要素の型も、クエリを実行する `For Each` ステートメントで使用されるループコントロール変数の型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="81022-110">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="81022-111">この厳密な型指定により、コンパイル時に型エラーの識別が容易になります。</span><span class="sxs-lookup"><span data-stu-id="81022-111">This strong typing facilitates identification of type errors at compile time.</span></span>

<span data-ttu-id="81022-112">Visual Basic は、*暗黙的*な型指定とも呼ばれるローカル型推論を実装することによって、厳密な型指定を容易にします。</span><span class="sxs-lookup"><span data-stu-id="81022-112">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="81022-113">この機能は、前の例で使用されており、[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] のサンプルとドキュメント全体で使用されています。</span><span class="sxs-lookup"><span data-stu-id="81022-113">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] samples and documentation.</span></span> <span data-ttu-id="81022-114">Visual Basic では、ローカル型の推論は、`As` 句を指定せずに `Dim` ステートメントを使用するだけで行われます。</span><span class="sxs-lookup"><span data-stu-id="81022-114">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="81022-115">次の例では、`city` が文字列として厳密に型指定されています。</span><span class="sxs-lookup"><span data-stu-id="81022-115">In the following example, `city` is strongly typed as a string.</span></span>

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="81022-116">ローカル型の推論は、`Option Infer` が `On` に設定されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="81022-116">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="81022-117">詳細については、「 [Option 推論ステートメント](../../../../visual-basic/language-reference/statements/option-infer-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81022-117">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>

<span data-ttu-id="81022-118">ただし、クエリでローカル型の推論を使用する場合でも、データソース内の変数、クエリ変数、およびクエリ実行ループの間に同じ型のリレーションシップが存在します。</span><span class="sxs-lookup"><span data-stu-id="81022-118">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="81022-119">@No__t_0 のクエリを記述する場合や、ドキュメントのサンプルやコード例を使用する場合は、これらの型の関係を基本的に理解しておくと便利です。</span><span class="sxs-lookup"><span data-stu-id="81022-119">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, or working with the samples and code examples in the documentation.</span></span>

<span data-ttu-id="81022-120">データソースから返される型と一致しない範囲変数には、明示的な型を指定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="81022-120">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="81022-121">@No__t_0 句を使用して、範囲変数の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="81022-121">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="81022-122">ただし、変換が[縮小変換](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)であり、`Option Strict` が `On` に設定されている場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="81022-122">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="81022-123">したがって、データソースから取得した値に対して変換を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="81022-123">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="81022-124">@No__t_0 メソッドを使用して、データソースの値を明示的な範囲変数型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="81022-124">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="81022-125">また、`Select` 句で選択した値を、範囲変数の型とは異なる明示的な型にキャストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="81022-125">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="81022-126">これらの点を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="81022-126">These points are illustrated in the following code.</span></span>

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="81022-127">ソースデータの要素全体を返すクエリ</span><span class="sxs-lookup"><span data-stu-id="81022-127">Queries That Return Entire Elements of the Source Data</span></span>

<span data-ttu-id="81022-128">次の例は、ソースデータから選択された一連の要素を返す [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] クエリ操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="81022-128">The following example shows a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="81022-129">Source、`names` には文字列の配列が含まれており、クエリ出力は、文字 M で始まる文字列を含むシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="81022-129">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

<span data-ttu-id="81022-130">これは次のコードと同じですが、はるかに短く、簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="81022-130">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="81022-131">クエリでのローカル型の推定への依存は、Visual Basic で推奨されるスタイルです。</span><span class="sxs-lookup"><span data-stu-id="81022-131">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

<span data-ttu-id="81022-132">前のコード例では、型が暗黙的または明示的に決定されているかどうかに関係があります。</span><span class="sxs-lookup"><span data-stu-id="81022-132">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>

1. <span data-ttu-id="81022-133">データソース内の要素の型である `names` は、クエリ内の範囲変数の型 `name` です。</span><span class="sxs-lookup"><span data-stu-id="81022-133">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>

2. <span data-ttu-id="81022-134">選択されているオブジェクトの種類 (`name`) によって、クエリ変数の型 `mNames` が決まります。</span><span class="sxs-lookup"><span data-stu-id="81022-134">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="81022-135">ここで `name` は文字列なので、クエリ変数は Visual Basic の IEnumerable (Of String) です。</span><span class="sxs-lookup"><span data-stu-id="81022-135">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>

3. <span data-ttu-id="81022-136">@No__t_0 で定義されたクエリは、`For Each` ループで実行されます。</span><span class="sxs-lookup"><span data-stu-id="81022-136">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="81022-137">ループは、クエリの実行結果を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="81022-137">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="81022-138">@No__t_0 実行すると、は文字列のシーケンスを返し、ループ反復変数、`nm` も文字列になります。</span><span class="sxs-lookup"><span data-stu-id="81022-138">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>

## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="81022-139">選択した要素から1つのフィールドを返すクエリ</span><span class="sxs-lookup"><span data-stu-id="81022-139">Queries That Return One Field from Selected Elements</span></span>

<span data-ttu-id="81022-140">次の例は、データソースから選択された各要素の1つの部分のみを含むシーケンスを返す [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] クエリ操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="81022-140">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="81022-141">このクエリは、データソースとして `Customer` オブジェクトのコレクションを取得し、結果の `Name` プロパティのみを射影します。</span><span class="sxs-lookup"><span data-stu-id="81022-141">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="81022-142">顧客名は文字列であるため、クエリは文字列のシーケンスを出力として生成します。</span><span class="sxs-lookup"><span data-stu-id="81022-142">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim custNames = From cust In customers
                Where cust.City = "London"
                Select cust.Name

For Each custName In custNames
    Console.WriteLine(custName)
Next
```

<span data-ttu-id="81022-143">変数間のリレーションシップは、単純な例の場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="81022-143">The relationships between variables are like those in the simpler example.</span></span>

1. <span data-ttu-id="81022-144">データソース内の要素の型である `customers` は、クエリ内の範囲変数の型 `cust` です。</span><span class="sxs-lookup"><span data-stu-id="81022-144">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="81022-145">この例では、この型は `Customer` です。</span><span class="sxs-lookup"><span data-stu-id="81022-145">In this example, that type is `Customer`.</span></span>

2. <span data-ttu-id="81022-146">@No__t_0 ステートメントは、オブジェクト全体ではなく、各 `Customer` オブジェクトの `Name` プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="81022-146">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="81022-147">@No__t_0 が文字列であるため、クエリ変数の `custNames` は、`Customer` ではなく、IEnumerable (Of String) になります。</span><span class="sxs-lookup"><span data-stu-id="81022-147">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>

3. <span data-ttu-id="81022-148">@No__t_0 は文字列のシーケンスを表すため、`For Each` ループの反復変数 `custName` は文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="81022-148">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>

<span data-ttu-id="81022-149">次の例に示すように、ローカル型の推定を使用しない場合、前の例では記述と理解が煩雑になります。</span><span class="sxs-lookup"><span data-stu-id="81022-149">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()
 Dim custNames As IEnumerable(Of String) =
     From cust As Customer In customers
     Where cust.City = "London"
     Select cust.Name

 For Each custName As String In custNames
     Console.WriteLine(custName)
 Next
```

## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="81022-150">匿名型を必要とするクエリ</span><span class="sxs-lookup"><span data-stu-id="81022-150">Queries That Require Anonymous Types</span></span>

<span data-ttu-id="81022-151">次の例は、より複雑な状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="81022-151">The following example shows a more complex situation.</span></span> <span data-ttu-id="81022-152">前の例では、すべての変数の型を明示的に指定するのは不便でした。</span><span class="sxs-lookup"><span data-stu-id="81022-152">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="81022-153">この例では、これは不可能です。</span><span class="sxs-lookup"><span data-stu-id="81022-153">In this example, it is impossible.</span></span> <span data-ttu-id="81022-154">このクエリの `Select` 句は、データソースの `Customer` 要素全体、または各要素の1つのフィールドを選択するのではなく、元の `Customer` オブジェクトの2つのプロパティ `Name` と `City` を返します。</span><span class="sxs-lookup"><span data-stu-id="81022-154">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="81022-155">@No__t_0 句に対する応答として、コンパイラは、これら2つのプロパティを含む匿名型を定義します。</span><span class="sxs-lookup"><span data-stu-id="81022-155">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="81022-156">@No__t_1 ループで `nameCityQuery` を実行した結果は、新しい匿名型のインスタンスのコレクションになります。</span><span class="sxs-lookup"><span data-stu-id="81022-156">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="81022-157">匿名型には使用可能な名前がないため、`nameCityQuery` の型や `custInfo` 明示的に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="81022-157">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="81022-158">つまり、匿名型の場合、`IEnumerable(Of String)` の `String` の代わりに使用する型名はありません。</span><span class="sxs-lookup"><span data-stu-id="81022-158">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="81022-159">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81022-159">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim nameCityQuery = From cust In customers
                    Where cust.City = "London"
                    Select cust.Name, cust.City

For Each custInfo In nameCityQuery
    Console.WriteLine(custInfo.Name)
Next
```

<span data-ttu-id="81022-160">前の例のすべての変数の型を指定することはできませんが、リレーションシップは同じままです。</span><span class="sxs-lookup"><span data-stu-id="81022-160">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>

1. <span data-ttu-id="81022-161">データソース内の要素の型は、クエリ内の範囲変数の型になります。</span><span class="sxs-lookup"><span data-stu-id="81022-161">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="81022-162">この例では、`cust` は `Customer` のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="81022-162">In this example, `cust` is an instance of `Customer`.</span></span>

2. <span data-ttu-id="81022-163">@No__t_0 ステートメントによって匿名型が生成されるため、クエリ変数の `nameCityQuery` は、匿名型として暗黙的に型指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81022-163">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="81022-164">匿名型には使用可能な名前がないため、明示的に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="81022-164">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>

3. <span data-ttu-id="81022-165">@No__t_0 ループ内の反復変数の型は、手順 2. で作成した匿名型です。</span><span class="sxs-lookup"><span data-stu-id="81022-165">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="81022-166">型には使用可能な名前がないため、ループ反復変数の型を暗黙的に決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81022-166">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>

## <a name="see-also"></a><span data-ttu-id="81022-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="81022-167">See also</span></span>

- [<span data-ttu-id="81022-168">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="81022-168">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="81022-169">匿名型</span><span class="sxs-lookup"><span data-stu-id="81022-169">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="81022-170">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="81022-170">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="81022-171">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="81022-171">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="81022-172">LINQ</span><span class="sxs-lookup"><span data-stu-id="81022-172">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="81022-173">クエリ</span><span class="sxs-lookup"><span data-stu-id="81022-173">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
