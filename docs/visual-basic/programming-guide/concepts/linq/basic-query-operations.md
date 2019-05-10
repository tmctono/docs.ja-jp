---
title: 基本的なクエリ操作 (Visual Basic)
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
ms.openlocfilehash: af99a6c22239be1f9f03bafd8323c73f83df5c51
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642273"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="92891-102">基本的なクエリ操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92891-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="92891-103">このトピックで説明を簡単に紹介[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]Visual Basic、およびいくつかのクエリを実行する操作の一般的な種類の式。</span><span class="sxs-lookup"><span data-stu-id="92891-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="92891-104">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92891-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="92891-105">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="92891-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="92891-106">クエリ</span><span class="sxs-lookup"><span data-stu-id="92891-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="92891-107">チュートリアル: Visual Basic におけるクエリの作成</span><span class="sxs-lookup"><span data-stu-id="92891-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="92891-108">(From) データ ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="92891-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="92891-109">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]のクエリでは、まず、クエリを実行するデータ ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="92891-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="92891-110">そのため、`From`クエリ句は常に最初は。</span><span class="sxs-lookup"><span data-stu-id="92891-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="92891-111">クエリ演算子は、選択し、図形のソースの種類に基づく結果。</span><span class="sxs-lookup"><span data-stu-id="92891-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="92891-112">`From`句は、データ ソースを指定`customers`、および*範囲変数*、`cust`します。</span><span class="sxs-lookup"><span data-stu-id="92891-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="92891-113">範囲変数は、クエリ式では、実際の反復は発生しませんが、ループの反復変数のようなは。</span><span class="sxs-lookup"><span data-stu-id="92891-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="92891-114">クエリが実行されると、多くの場合を使用して、`For Each`ループ、連続する各要素への参照として範囲変数`customers`します。</span><span class="sxs-lookup"><span data-stu-id="92891-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="92891-115">`cust` の型はコンパイラで推論できるため、明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="92891-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="92891-116">明示的な型指定なしで記述されたクエリの例については、次を参照してください。[クエリ操作 (Visual Basic) での型の関係](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="92891-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="92891-117">使用する方法についての詳細、 `From` Visual basic での句を参照してください[句から](../../../../visual-basic/language-reference/queries/from-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="92891-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="92891-118">データのフィルター処理 (場所)</span><span class="sxs-lookup"><span data-stu-id="92891-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="92891-119">おそらく、最も一般的なクエリ操作では、ブール式の形式でフィルターを適用するは。</span><span class="sxs-lookup"><span data-stu-id="92891-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="92891-120">クエリは、式が true の要素のみを返します。</span><span class="sxs-lookup"><span data-stu-id="92891-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="92891-121">A`Where`句を使用して、フィルター処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="92891-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="92891-122">フィルターは、結果のシーケンスに含めるデータ ソース内のどの要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="92891-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="92891-123">次の例では、住所がロンドンを持つお客様のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92891-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="92891-124">などの論理演算子を使用することができます`And`と`Or`のフィルター式を結合する、`Where`句。</span><span class="sxs-lookup"><span data-stu-id="92891-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="92891-125">たとえば、ロンドンし、名前を持つ、デボン顧客のみを返すには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="92891-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="92891-126">ロンドンまたはパリにある顧客を返すには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="92891-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="92891-127">使用する方法についての詳細、 `Where` Visual basic での句を参照してください[Where 句](../../../../visual-basic/language-reference/queries/where-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="92891-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="92891-128">データ (Order By) の並べ替え</span><span class="sxs-lookup"><span data-stu-id="92891-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="92891-129">多くの場合は、特定の順序に返されるデータを並べ替えると便利です。</span><span class="sxs-lookup"><span data-stu-id="92891-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="92891-130">`Order By`句には、指定されたフィールドで並べ替えるに返されたシーケンスで要素が発生します。</span><span class="sxs-lookup"><span data-stu-id="92891-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="92891-131">たとえば、次のクエリがに基づいて結果を並べ替えます、`Name`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92891-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="92891-132">`Name`文字列では、a ~ Z、返されるデータは、アルファベット順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="92891-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="92891-133">結果を逆の順序 (Z から A) で並び替えるには、`Order By...Descending` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="92891-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="92891-134">既定値は`Ascending`がいずれも`Ascending`も`Descending`を指定します。</span><span class="sxs-lookup"><span data-stu-id="92891-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="92891-135">使用する方法についての詳細、 `Order By` Visual basic での句を参照してください[Order By 句](../../../../visual-basic/language-reference/queries/order-by-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="92891-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="92891-136">データ (選択) を選択します。</span><span class="sxs-lookup"><span data-stu-id="92891-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="92891-137">`Select`句は、フォームと返される要素の内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="92891-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="92891-138">完全な結果はで構成されているかどうかを指定するたとえば、`Customer`オブジェクト、1 つにすぎません`Customer`計算に基づいて、プロパティ、プロパティのサブセット、さまざまなデータ ソース、または新しい結果の種類からのプロパティの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="92891-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="92891-139">`Select` 句でソース要素のコピー以外のものを生成する場合、その操作は*投影*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="92891-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="92891-140">完全なから成るコレクションを取得する`Customer`オブジェクト、範囲変数自体を選択します。</span><span class="sxs-lookup"><span data-stu-id="92891-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="92891-141">場合、`Customer`インスタンスは、ラージ オブジェクトを持つ多くのフィールドと名前を取得することだけですを選択できます`cust.Name`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="92891-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="92891-142">ローカル型推論のコレクションから結果の型が変更される`Customer`オブジェクトを文字列のコレクション。</span><span class="sxs-lookup"><span data-stu-id="92891-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="92891-143">データ ソースから複数のフィールドを選択するには、2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="92891-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="92891-144">`Select`句では、結果に含めるフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="92891-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="92891-145">コンパイラは、それらのフィールドとしてそのプロパティを含む匿名型を定義します。</span><span class="sxs-lookup"><span data-stu-id="92891-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="92891-146">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92891-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="92891-147">次の例で返される要素は、匿名型のインスタンスであるため、参照できません型に名前で別の場所、コード内。</span><span class="sxs-lookup"><span data-stu-id="92891-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="92891-148">コンパイラの指定、型名には、通常の Visual Basic コードでは無効な文字が含まれています。</span><span class="sxs-lookup"><span data-stu-id="92891-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="92891-149">次の例では、クエリでは、によって返されるコレクション内の要素で`londonCusts4`匿名型のインスタンスであります。</span><span class="sxs-lookup"><span data-stu-id="92891-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="92891-150">- または -</span><span class="sxs-lookup"><span data-stu-id="92891-150">-or-</span></span>  
  
- <span data-ttu-id="92891-151">結果に含まれるを作成し、型のインスタンスを初期化する特定のフィールドを含む名前付きの型を定義、`Select`句。</span><span class="sxs-lookup"><span data-stu-id="92891-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="92891-152">これらは、返される、コレクションの外部の個別の結果を使用する必要がある場合にのみ、またはメソッドの呼び出しでパラメーターとして渡すことがある場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="92891-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="92891-153">型`londonCusts5`次の例では、IEnumerable (Of NamePhone)。</span><span class="sxs-lookup"><span data-stu-id="92891-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="92891-154">使用する方法についての詳細、 `Select` Visual basic での句を参照してください[Select 句](../../../../visual-basic/language-reference/queries/select-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="92891-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="92891-155">結合のデータ (結合やグループ結合)</span><span class="sxs-lookup"><span data-stu-id="92891-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="92891-156">複数のデータ ソースを組み合わせることができます、`From`いくつかの方法で句。</span><span class="sxs-lookup"><span data-stu-id="92891-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="92891-157">たとえば、次のコードでは、2 つのデータ ソースを使用して、暗黙的に結果にこれらの両方からのプロパティを結合します。</span><span class="sxs-lookup"><span data-stu-id="92891-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="92891-158">クエリでは、母音で始まる最後名前受講者を選択します。</span><span class="sxs-lookup"><span data-stu-id="92891-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
>  <span data-ttu-id="92891-159">作成した受講者の一覧で、このコードを実行することができます[方法。項目の一覧を作成](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="92891-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="92891-160">`Join`キーワードは、 `INNER JOIN` sql です。</span><span class="sxs-lookup"><span data-stu-id="92891-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="92891-161">これは、2 つのコレクション内の要素間の一致するキー値に基づいて 2 つのコレクションを結合します。</span><span class="sxs-lookup"><span data-stu-id="92891-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="92891-162">クエリでは、キーの値が一致するコレクションの要素のすべてまたは一部を返します。</span><span class="sxs-lookup"><span data-stu-id="92891-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="92891-163">たとえば、次のコードでは、前の暗黙の結合のアクションが重複しています。</span><span class="sxs-lookup"><span data-stu-id="92891-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="92891-164">`Group Join` 同じようにコレクションを 1 つの階層コレクションを組み合わせて、 `LEFT JOIN` sql です。</span><span class="sxs-lookup"><span data-stu-id="92891-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="92891-165">詳細については、次を参照してください。 [Join 句](../../../../visual-basic/language-reference/queries/join-clause.md)と[Group Join 句](../../../../visual-basic/language-reference/queries/group-join-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="92891-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="92891-166">データのグループ化 (Group By)</span><span class="sxs-lookup"><span data-stu-id="92891-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="92891-167">追加することができます、`Group By`要素の 1 つまたは複数のフィールドに従ってのクエリ結果内の要素をグループ化する句。</span><span class="sxs-lookup"><span data-stu-id="92891-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="92891-168">たとえば、次のコードでは、クラス年ごと学生をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="92891-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="92891-169">作成した受講者のリストを使用してこのコードを実行するかどうかは[方法。リストの項目を作成](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)からの出力、`For Each`ステートメントは。</span><span class="sxs-lookup"><span data-stu-id="92891-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="92891-170">年。Junior</span><span class="sxs-lookup"><span data-stu-id="92891-170">Year: Junior</span></span>  
  
 <span data-ttu-id="92891-171">Tucker です、Michael</span><span class="sxs-lookup"><span data-stu-id="92891-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="92891-172">Garcia、Hugo</span><span class="sxs-lookup"><span data-stu-id="92891-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="92891-173">Garcia、Debra</span><span class="sxs-lookup"><span data-stu-id="92891-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="92891-174">Lance、tucker です。</span><span class="sxs-lookup"><span data-stu-id="92891-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="92891-175">年。シニア</span><span class="sxs-lookup"><span data-stu-id="92891-175">Year: Senior</span></span>  
  
 <span data-ttu-id="92891-176">Omelchenko、Svetlana</span><span class="sxs-lookup"><span data-stu-id="92891-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="92891-177">田山、Michiko</span><span class="sxs-lookup"><span data-stu-id="92891-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="92891-178">Fakhouri、Fadi</span><span class="sxs-lookup"><span data-stu-id="92891-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="92891-179">Feng、ある Hanying</span><span class="sxs-lookup"><span data-stu-id="92891-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="92891-180">Terry Adams は、</span><span class="sxs-lookup"><span data-stu-id="92891-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="92891-181">年。今</span><span class="sxs-lookup"><span data-stu-id="92891-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="92891-182">Mortensen、Sven</span><span class="sxs-lookup"><span data-stu-id="92891-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="92891-183">Garcia、Cesar</span><span class="sxs-lookup"><span data-stu-id="92891-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="92891-184">次のコードに示すように、バリエーションの 1 つは、並べ替え、クラスの年を姓で各年度、受講者を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="92891-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="92891-185">詳細については`Group By`を参照してください[By 句のグループ](../../../../visual-basic/language-reference/queries/group-by-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="92891-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92891-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="92891-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="92891-187">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="92891-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="92891-188">クエリ</span><span class="sxs-lookup"><span data-stu-id="92891-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="92891-189">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92891-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="92891-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="92891-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
