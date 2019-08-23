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
ms.openlocfilehash: 12f10f30dd767f3435044f2bbebe0eb865c29d0c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939373"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="cc533-102">基本的なクエリ操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc533-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="cc533-103">このトピックでは、Visual Basic の[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]式と、クエリで実行する一般的な操作の一部について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="cc533-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="cc533-104">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="cc533-105">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="cc533-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="cc533-106">クエリ</span><span class="sxs-lookup"><span data-stu-id="cc533-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="cc533-107">チュートリアル: Visual Basic でのクエリの作成</span><span class="sxs-lookup"><span data-stu-id="cc533-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="cc533-108">データソースの指定 (から)</span><span class="sxs-lookup"><span data-stu-id="cc533-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="cc533-109">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]クエリでは、最初の手順として、クエリを実行するデータソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc533-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="cc533-110">そのため、 `From`クエリの句は常に最初になります。</span><span class="sxs-lookup"><span data-stu-id="cc533-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="cc533-111">クエリ演算子ソースの種類に基づいて、結果を選択して整形します。</span><span class="sxs-lookup"><span data-stu-id="cc533-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="cc533-112">句では、データ`customers`ソース、、 `cust`および*範囲変数*を指定します。 `From`</span><span class="sxs-lookup"><span data-stu-id="cc533-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="cc533-113">範囲変数はループ反復変数に似ていますが、クエリ式では実際のイテレーションは発生しません。</span><span class="sxs-lookup"><span data-stu-id="cc533-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="cc533-114">クエリが実行されると、多くの場合`For Each` 、ループを使用して、範囲変数はの`customers`連続する各要素への参照として機能します。</span><span class="sxs-lookup"><span data-stu-id="cc533-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="cc533-115">`cust` の型はコンパイラで推論できるため、明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cc533-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="cc533-116">明示的な型指定なしで記述されたクエリの例については、「[クエリ操作での型の関係 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="cc533-117">Visual Basic で`From`句を使用する方法の詳細については、「 [from 句](../../../../visual-basic/language-reference/queries/from-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="cc533-118">データのフィルター処理 (Where)</span><span class="sxs-lookup"><span data-stu-id="cc533-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="cc533-119">最も一般的なクエリ操作では、ブール式の形式でフィルターが適用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc533-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="cc533-120">次に、式が true になっている要素のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="cc533-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="cc533-121">`Where`句は、フィルター処理を実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc533-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="cc533-122">フィルターでは、結果のシーケンスに含めるデータソース内の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc533-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="cc533-123">次の例では、ロンドンに住所を持つ顧客のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc533-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="cc533-124">やなど`And`の論理演算子を使用する`Or`と、 `Where`句でフィルター式を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="cc533-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="cc533-125">たとえば、名前が Devon であるロンドンからの顧客のみを返すには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc533-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="cc533-126">ロンドンまたはパリの顧客を返すには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc533-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="cc533-127">Visual Basic で`Where`句を使用する方法の詳細については、「 [Where 句](../../../../visual-basic/language-reference/queries/where-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="cc533-128">データの並べ替え (Order By)</span><span class="sxs-lookup"><span data-stu-id="cc533-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="cc533-129">多くの場合、返されたデータを特定の順序に並べ替えると便利です。</span><span class="sxs-lookup"><span data-stu-id="cc533-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="cc533-130">`Order By`句により、返されたシーケンス内の要素が、指定されたフィールドで並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="cc533-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="cc533-131">たとえば、次のクエリでは、 `Name`プロパティに基づいて結果が並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="cc533-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="cc533-132">は`Name`文字列であるため、返されるデータはアルファベット順 (a から Z) に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="cc533-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="cc533-133">結果を逆の順序 (Z から A) で並び替えるには、`Order By...Descending` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc533-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="cc533-134">と`Ascending` が`Descending`どちらも`Ascending`指定されていない場合、既定値はです。</span><span class="sxs-lookup"><span data-stu-id="cc533-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="cc533-135">Visual Basic で`Order By`句を使用する方法の詳細については、「 [order by 句](../../../../visual-basic/language-reference/queries/order-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="cc533-136">データの選択 (Select)</span><span class="sxs-lookup"><span data-stu-id="cc533-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="cc533-137">句`Select`は、返される要素のフォームとコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc533-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="cc533-138">たとえば、結果を、完全`Customer`なオブジェクト、1つのプロパティ、プロパティのサブセット、さまざまなデータソースからのプロパティの組み合わせ、または計算に基づいた新しい結果型のいずれ`Customer`で構成するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc533-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="cc533-139">`Select` 句でソース要素のコピー以外のものを生成する場合、その操作は*投影*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cc533-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="cc533-140">完全な`Customer`オブジェクトで構成されるコレクションを取得するには、範囲変数自体を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc533-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="cc533-141">インスタンスが多数のフィールドを持つ大きなオブジェクトで、取得するすべてのが名前である場合は、次の例に`cust.Name`示すようにを選択できます。 `Customer`</span><span class="sxs-lookup"><span data-stu-id="cc533-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="cc533-142">ローカル型の推論では、結果の型がオブジェクトの`Customer`コレクションから文字列のコレクションに変更されることが認識されます。</span><span class="sxs-lookup"><span data-stu-id="cc533-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="cc533-143">データソースから複数のフィールドを選択するには、次の2つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="cc533-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="cc533-144">`Select`句で、結果に含めるフィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc533-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="cc533-145">コンパイラは、これらのフィールドをプロパティとして持つ匿名型を定義します。</span><span class="sxs-lookup"><span data-stu-id="cc533-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="cc533-146">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="cc533-147">次の例で返される要素は匿名型のインスタンスなので、コード内の他の場所で型を名前で参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc533-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="cc533-148">コンパイラによって指定された型の名前に、通常の Visual Basic コードでは無効な文字が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc533-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="cc533-149">次の例では、の`londonCusts4`クエリによって返されるコレクション内の要素は匿名型のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="cc533-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="cc533-150">\- または -</span><span class="sxs-lookup"><span data-stu-id="cc533-150">-or-</span></span>  
  
- <span data-ttu-id="cc533-151">結果に含める特定のフィールドを含む名前付きの型を定義し、 `Select`句でその型のインスタンスを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="cc533-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="cc533-152">このオプションは、返されるコレクションの外部で個々の結果を使用する必要がある場合、またはメソッドの呼び出しでパラメーターとして渡す必要がある場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="cc533-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="cc533-153">次の例`londonCusts5`のの型は IEnumerable (namephone) です。</span><span class="sxs-lookup"><span data-stu-id="cc533-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="cc533-154">Visual Basic で`Select`句を使用する方法の詳細については、「 [Select 句](../../../../visual-basic/language-reference/queries/select-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="cc533-155">データの結合 (結合とグループ結合)</span><span class="sxs-lookup"><span data-stu-id="cc533-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="cc533-156">`From`句で複数のデータソースを組み合わせるには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="cc533-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="cc533-157">たとえば、次のコードでは、2つのデータソースを使用し、両方のプロパティを結果に暗黙的に結合しています。</span><span class="sxs-lookup"><span data-stu-id="cc533-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="cc533-158">このクエリでは、姓が母音で始まる学生を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc533-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="cc533-159">次の方法で[作成された学生の一覧を使用して、このコードを実行できます。項目](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="cc533-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="cc533-160">キーワードは、 `INNER JOIN` SQL のに相当します。 `Join`</span><span class="sxs-lookup"><span data-stu-id="cc533-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="cc533-161">2つのコレクションの要素間でのキー値の一致に基づいて、2つのコレクションを結合します。</span><span class="sxs-lookup"><span data-stu-id="cc533-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="cc533-162">このクエリでは、キー値が一致するコレクション要素のすべてまたは一部が返されます。</span><span class="sxs-lookup"><span data-stu-id="cc533-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="cc533-163">たとえば、次のコードでは、前の暗黙的な結合のアクションが複製されます。</span><span class="sxs-lookup"><span data-stu-id="cc533-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="cc533-164">`Group Join`は、SQL のの場合`LEFT JOIN`と同様に、コレクションを1つの階層コレクションに結合します。</span><span class="sxs-lookup"><span data-stu-id="cc533-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="cc533-165">詳細については、「 [Join 句](../../../../visual-basic/language-reference/queries/join-clause.md)と[Group join 句](../../../../visual-basic/language-reference/queries/group-join-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="cc533-166">データのグループ化 (Group By)</span><span class="sxs-lookup"><span data-stu-id="cc533-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="cc533-167">句を`Group By`追加すると、要素の1つまたは複数のフィールドに従って、クエリ結果の要素をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="cc533-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="cc533-168">たとえば、次のコードでは、学生をクラス年別にグループ化しています。</span><span class="sxs-lookup"><span data-stu-id="cc533-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="cc533-169">次の方法で[作成された学生の一覧を使用してこのコードを実行する場合:項目](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)の一覧を作成すると、 `For Each`ステートメントからの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cc533-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="cc533-170">比新任</span><span class="sxs-lookup"><span data-stu-id="cc533-170">Year: Junior</span></span>  
  
 <span data-ttu-id="cc533-171">Tucker、Michael</span><span class="sxs-lookup"><span data-stu-id="cc533-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="cc533-172">お金</span><span class="sxs-lookup"><span data-stu-id="cc533-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="cc533-173">Debra、</span><span class="sxs-lookup"><span data-stu-id="cc533-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="cc533-174">Tucker、Lance</span><span class="sxs-lookup"><span data-stu-id="cc533-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="cc533-175">比シニア</span><span class="sxs-lookup"><span data-stu-id="cc533-175">Year: Senior</span></span>  
  
 <span data-ttu-id="cc533-176">Omelchenko、Svetlana</span><span class="sxs-lookup"><span data-stu-id="cc533-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="cc533-177">Osada、Michiko</span><span class="sxs-lookup"><span data-stu-id="cc533-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="cc533-178">Fakhouri、Fadi</span><span class="sxs-lookup"><span data-stu-id="cc533-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="cc533-179">Feng</span><span class="sxs-lookup"><span data-stu-id="cc533-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="cc533-180">Adams、マネージャー</span><span class="sxs-lookup"><span data-stu-id="cc533-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="cc533-181">比Freshman</span><span class="sxs-lookup"><span data-stu-id="cc533-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="cc533-182">Sven</span><span class="sxs-lookup"><span data-stu-id="cc533-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="cc533-183">Cesar、</span><span class="sxs-lookup"><span data-stu-id="cc533-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="cc533-184">次のコードに示すバリエーションでは、クラス年を順に並べ替え、各年の各学生を姓で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="cc533-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="cc533-185">の詳細`Group By`については、「 [group by 句](../../../../visual-basic/language-reference/queries/group-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc533-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc533-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc533-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="cc533-187">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="cc533-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="cc533-188">クエリ</span><span class="sxs-lookup"><span data-stu-id="cc533-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="cc533-189">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc533-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="cc533-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="cc533-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
