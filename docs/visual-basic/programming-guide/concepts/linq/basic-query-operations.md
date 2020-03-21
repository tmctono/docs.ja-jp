---
title: クエリの基本操作
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266379"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="e12a0-102">基本的なクエリ操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e12a0-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="e12a0-103">このトピックでは、Visual Basic での統合言語クエリ (LINQ) 式の概要と、クエリで実行する一般的な種類の操作の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="e12a0-104">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="e12a0-105">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="e12a0-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="e12a0-106">クエリ</span><span class="sxs-lookup"><span data-stu-id="e12a0-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="e12a0-107">チュートリアル: Visual Basic でクエリを記述する</span><span class="sxs-lookup"><span data-stu-id="e12a0-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="e12a0-108">データ ソースの指定 (元)</span><span class="sxs-lookup"><span data-stu-id="e12a0-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="e12a0-109">LINQ クエリでは、最初にクエリを実行するデータ ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="e12a0-110">したがって、クエリ`From`内の句が常に最初に来ます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="e12a0-111">クエリ演算子は、ソースの種類に基づいて結果を選択し、その結果を形成します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="e12a0-112">句`From`では、データ ソース`customers`、および*範囲変数*、`cust`を指定します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="e12a0-113">範囲変数はループ反復変数に似ていますが、クエリ式では実際の反復は発生しません。</span><span class="sxs-lookup"><span data-stu-id="e12a0-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="e12a0-114">クエリを実行する場合、多くの場合ループ`For Each`を使用して、範囲変数は、 の`customers`連続する各要素への参照として機能します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="e12a0-115">`cust` の型はコンパイラで推論できるため、明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e12a0-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="e12a0-116">明示的な型指定の有無にかかわらず作成されるクエリの例については、「[クエリ操作での型の関係 (Visual Basic)」](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="e12a0-117">Visual Basic で句を`From`使用する方法の詳細については、「 From 句 」を[参照](../../../../visual-basic/language-reference/queries/from-clause.md)してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="e12a0-118">データのフィルタリング (場所)</span><span class="sxs-lookup"><span data-stu-id="e12a0-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="e12a0-119">おそらく最も一般的なクエリ操作は、ブール式の形式でフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="e12a0-120">クエリは、式が true である要素のみを返します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="e12a0-121">句`Where`は、フィルタ処理を実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="e12a0-122">フィルターは、結果のシーケンスに含めるデータ ソース内の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="e12a0-123">次の例では、ロンドンに住所を持つ顧客のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e12a0-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="e12a0-124">などの論理演算子を使用して`And`、`Or`句内のフィルター式を`Where`組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="e12a0-125">たとえば、ロンドン出身で、名前が Devon である顧客のみを返す場合は、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="e12a0-126">ロンドンまたはパリから顧客を返すには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="e12a0-127">Visual Basic で句を`Where`使用する方法の詳細については[、「WHERE 句](../../../../visual-basic/language-reference/queries/where-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="e12a0-128">データの順序 (発注順)</span><span class="sxs-lookup"><span data-stu-id="e12a0-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="e12a0-129">多くの場合、返されたデータを特定の順序に並べ替えるのが便利です。</span><span class="sxs-lookup"><span data-stu-id="e12a0-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="e12a0-130">句`Order By`は、返されたシーケンス内の要素が、指定された 1 つまたは複数のフィールドに並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="e12a0-131">たとえば、次のクエリは、プロパティに基づいて結果`Name`を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="e12a0-132">文字列`Name`であるため、返されるデータはアルファベット順に A から Z に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="e12a0-133">結果を逆の順序 (Z から A) で並び替えるには、`Order By...Descending` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="e12a0-134">デフォルトは、`Ascending`指定も`Ascending`指定`Descending`もされていない場合です。</span><span class="sxs-lookup"><span data-stu-id="e12a0-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="e12a0-135">Visual Basic で句を`Order By`使用する方法の詳細については、「[句の順序](../../../../visual-basic/language-reference/queries/order-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="e12a0-136">データの選択 (選択)</span><span class="sxs-lookup"><span data-stu-id="e12a0-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="e12a0-137">句`Select`は、返される要素の形式と内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="e12a0-138">たとえば、結果が完全な`Customer`オブジェクト、1 つの`Customer`プロパティ、プロパティのサブセット、さまざまなデータ ソースのプロパティの組み合わせ、または計算に基づく新しい結果の種類で構成されるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="e12a0-139">`Select` 句でソース要素のコピー以外のものを生成する場合、その操作は*投影*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="e12a0-140">完全な`Customer`オブジェクトで構成されるコレクションを取得するには、範囲変数自体を選択します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="e12a0-141">`Customer`インスタンスが多数のフィールドを持つ大きなオブジェクトで、取得するオブジェクトが名前だけである場合は、次の例`cust.Name`に示すように を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="e12a0-142">ローカル型推論では、結果の型がオブジェクトのコレクションから文字列の`Customer`コレクションに変更されることを認識します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="e12a0-143">データ ソースから複数のフィールドを選択するには、次の 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="e12a0-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="e12a0-144">句で`Select`、結果に含めるフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="e12a0-145">コンパイラは、これらのフィールドをプロパティとして持つ匿名型を定義します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="e12a0-146">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="e12a0-147">次の例で返される要素は匿名型のインスタンスであるため、コード内の他の場所で名前で型を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="e12a0-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="e12a0-148">コンパイラが指定した型の名前に、通常の Visual Basic コードでは無効な文字が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e12a0-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="e12a0-149">次の例では、 クエリによって返されるコレクション内の要素`londonCusts4`は、匿名型のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="e12a0-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="e12a0-150">または</span><span class="sxs-lookup"><span data-stu-id="e12a0-150">-or-</span></span>  
  
- <span data-ttu-id="e12a0-151">結果に含める特定のフィールドを含む名前付きの型を定義し、その型のインスタンスを作成して、句内`Select`で初期化します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="e12a0-152">このオプションは、返されるコレクションの外部で個々の結果を使用する必要がある場合、またはメソッド呼び出しでパラメーターとして渡す必要がある場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="e12a0-153">次の例`londonCusts5`のタイプは、IEnumerable(ネームフォンの)です。</span><span class="sxs-lookup"><span data-stu-id="e12a0-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="e12a0-154">Visual Basic で句を使用`Select`する方法の詳細については、「[句の選択](../../../../visual-basic/language-reference/queries/select-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="e12a0-155">結合データ (結合およびグループ結合)</span><span class="sxs-lookup"><span data-stu-id="e12a0-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="e12a0-156">句内の複数のデータ ソースを`From`組み合わせる方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e12a0-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="e12a0-157">たとえば、次のコードでは 2 つのデータ ソースを使用し、両方のプロパティを結果に暗黙的に結合します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="e12a0-158">このクエリでは、母音で始まる姓の学生が選択されます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="e12a0-159">このコードは、「[方法 : アイテムのリストを作成する」で作成した学生のリストを](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="e12a0-160">キーワード`Join`は、SQL の`INNER JOIN`と同じです。</span><span class="sxs-lookup"><span data-stu-id="e12a0-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="e12a0-161">2 つのコレクションの要素間で一致するキー値に基づいて 2 つのコレクションを結合します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="e12a0-162">クエリは、一致するキー値を持つコレクション要素のすべてまたは一部を返します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="e12a0-163">たとえば、次のコードは、前の暗黙的な結合のアクションを複製します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="e12a0-164">`Group Join`コレクションを 1 つの階層コレクションに結合し、SQL`LEFT JOIN`の a と同じようにします。</span><span class="sxs-lookup"><span data-stu-id="e12a0-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="e12a0-165">詳細については、「[結合句](../../../../visual-basic/language-reference/queries/join-clause.md)と[グループ結合句](../../../../visual-basic/language-reference/queries/group-join-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="e12a0-166">データのグループ化 (グループ化)</span><span class="sxs-lookup"><span data-stu-id="e12a0-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="e12a0-167">句を`Group By`追加して、要素の 1 つ以上のフィールドに従ってクエリ結果の要素をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="e12a0-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="e12a0-168">たとえば、次のコードは、クラスの年で生徒をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="e12a0-169">「[方法: アイテム](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)のリストを作成する」で作成した学生のリストを使用してこのコードを実行すると`For Each`、ステートメントの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e12a0-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="e12a0-170">年: ジュニア</span><span class="sxs-lookup"><span data-stu-id="e12a0-170">Year: Junior</span></span>  
  
 <span data-ttu-id="e12a0-171">タッカー,マイケル</span><span class="sxs-lookup"><span data-stu-id="e12a0-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="e12a0-172">ガルシア,ヒューゴ</span><span class="sxs-lookup"><span data-stu-id="e12a0-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="e12a0-173">ガルシア,デブラ</span><span class="sxs-lookup"><span data-stu-id="e12a0-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="e12a0-174">タッカー,ランス</span><span class="sxs-lookup"><span data-stu-id="e12a0-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="e12a0-175">年: シニア</span><span class="sxs-lookup"><span data-stu-id="e12a0-175">Year: Senior</span></span>  
  
 <span data-ttu-id="e12a0-176">オメルチェンコ(スヴェトラーナ)</span><span class="sxs-lookup"><span data-stu-id="e12a0-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="e12a0-177">大田,美智子</span><span class="sxs-lookup"><span data-stu-id="e12a0-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="e12a0-178">ファクーリ(ファディ)</span><span class="sxs-lookup"><span data-stu-id="e12a0-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="e12a0-179">風(高輝)</span><span class="sxs-lookup"><span data-stu-id="e12a0-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="e12a0-180">アダムス,テリー</span><span class="sxs-lookup"><span data-stu-id="e12a0-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="e12a0-181">年: 新入生</span><span class="sxs-lookup"><span data-stu-id="e12a0-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="e12a0-182">モルテンセン(スヴェン)</span><span class="sxs-lookup"><span data-stu-id="e12a0-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="e12a0-183">ガルシア,セザール</span><span class="sxs-lookup"><span data-stu-id="e12a0-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="e12a0-184">次のコードに示すバリエーションは、クラス年を並べ替え、毎年の生徒に姓で注文します。</span><span class="sxs-lookup"><span data-stu-id="e12a0-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="e12a0-185">の詳細については、「`Group By`句[でグループ化](../../../../visual-basic/language-reference/queries/group-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e12a0-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12a0-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="e12a0-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="e12a0-187">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="e12a0-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="e12a0-188">クエリ</span><span class="sxs-lookup"><span data-stu-id="e12a0-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="e12a0-189">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e12a0-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="e12a0-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="e12a0-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
