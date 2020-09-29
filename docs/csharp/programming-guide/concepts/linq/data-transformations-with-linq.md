---
title: LINQ によるデータ変換 (C#)
description: C# で LINQ クエリを使用してデータを変換する方法について学習します。 並べ替えとグループ化を行ってシーケンスを変更し、select 句を使用して新しい型を作成できます。
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 2fb4166b9dbcecebf06b9dc3a780b02751dd4dc7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159151"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="c88c2-104">LINQ によるデータ変換 (C#)</span><span class="sxs-lookup"><span data-stu-id="c88c2-104">Data Transformations with LINQ (C#)</span></span>

<span data-ttu-id="c88c2-105">統合言語クエリ (LINQ) で行うことができるのは、データの取得だけではありません。</span><span class="sxs-lookup"><span data-stu-id="c88c2-105">Language-Integrated Query (LINQ) is not only about retrieving data.</span></span> <span data-ttu-id="c88c2-106">データ変換のための強力なツールとしても使用できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-106">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="c88c2-107">LINQ クエリを使用することにより、ソース シーケンスを入力として使用し、さまざまな方法で加工して新しい出力シーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-107">By using a LINQ query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="c88c2-108">要素自体を変更せずに、並べ替えやグループ化してシーケンス自体を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-108">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="c88c2-109">しかし、LINQ クエリの最も強力な機能は、新しい型を作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="c88c2-109">But perhaps the most powerful feature of LINQ queries is the ability to create new types.</span></span> <span data-ttu-id="c88c2-110">この操作は [select](../../../language-reference/keywords/select-clause.md) 句内で行います。</span><span class="sxs-lookup"><span data-stu-id="c88c2-110">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="c88c2-111">たとえば、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-111">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="c88c2-112">複数の入力シーケンスを結合して、新しい型の単一の出力シーケンスを作成する。</span><span class="sxs-lookup"><span data-stu-id="c88c2-112">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="c88c2-113">ソース シーケンス内の各要素の単一のプロパティまたは複数のプロパティを構成要素とする出力シーケンスを作成する。</span><span class="sxs-lookup"><span data-stu-id="c88c2-113">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="c88c2-114">ソース データに対して実行した操作の結果を構成要素とする出力シーケンスを作成する。</span><span class="sxs-lookup"><span data-stu-id="c88c2-114">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="c88c2-115">別の形式で出力シーケンスを作成する。</span><span class="sxs-lookup"><span data-stu-id="c88c2-115">Create output sequences in a different format.</span></span> <span data-ttu-id="c88c2-116">たとえば、SQL の行またはテキスト ファイルのデータを XML に変換できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-116">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="c88c2-117">これらはほんの一例です。</span><span class="sxs-lookup"><span data-stu-id="c88c2-117">These are just several examples.</span></span> <span data-ttu-id="c88c2-118">これらの変換を、同じクエリ内でさまざまな方法で組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-118">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="c88c2-119">また、あるクエリの出力シーケンスを別のクエリの入力シーケンスとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-119">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="c88c2-120">複数の入力を 1 つの出力シーケンスに結合する</span><span class="sxs-lookup"><span data-stu-id="c88c2-120">Joining Multiple Inputs into One Output Sequence</span></span>  

 <span data-ttu-id="c88c2-121">LINQ クエリを使用して、複数の入力シーケンスの要素を含む 1 つの出力シーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-121">You can use a LINQ query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="c88c2-122">次の例は、2 つのインメモリ データ構造を結合する方法を示していますが、ソースが XML、SQL、または DataSet のデータを結合する場合にも同じ基本原則を適用できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-122">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="c88c2-123">次の 2 つのクラス型があるとします。</span><span class="sxs-lookup"><span data-stu-id="c88c2-123">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="c88c2-124">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c88c2-124">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="c88c2-125">詳細については、「[join 句](../../../language-reference/keywords/join-clause.md)」および「[select 句](../../../language-reference/keywords/select-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88c2-125">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="c88c2-126">各ソース要素のサブセットを選択する</span><span class="sxs-lookup"><span data-stu-id="c88c2-126">Selecting a Subset of each Source Element</span></span>  

 <span data-ttu-id="c88c2-127">ソース シーケンスの各要素のサブセットを選択するには、主に次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c88c2-127">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="c88c2-128">ソース要素の 1 つのメンバーのみを選択するには、ドット演算を使用します。</span><span class="sxs-lookup"><span data-stu-id="c88c2-128">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="c88c2-129">次の例で、`Customer` オブジェクトに `City` という文字列を含むいくつかのパブリック プロパティが含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="c88c2-129">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="c88c2-130">このクエリを実行すると、文字列の出力シーケンスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-130">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="c88c2-131">ソース要素からの複数のプロパティを含む要素を作成するには、名前付きオブジェクトまたは匿名型を指定したオブジェクト初期化子を使用します。</span><span class="sxs-lookup"><span data-stu-id="c88c2-131">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="c88c2-132">次の例は、匿名型を使用して各 `Customer` 要素の 2 つのプロパティをカプセル化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c88c2-132">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="c88c2-133">詳細については、「[オブジェクト初期化子とコレクション初期化子](../../classes-and-structs/object-and-collection-initializers.md)」および「[匿名型](../../classes-and-structs/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88c2-133">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="c88c2-134">インメモリ オブジェクトを XML に変換する</span><span class="sxs-lookup"><span data-stu-id="c88c2-134">Transforming in-Memory Objects into XML</span></span>  

 <span data-ttu-id="c88c2-135">LINQ クエリを使用すると、インメモリ データ構造、SQL データベース、ADO.NET データセット、XML ストリーム、または XML ドキュメントの間でデータ変換を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-135">LINQ queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="c88c2-136">インメモリ データ構造のオブジェクトを XML 要素に変換する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c88c2-136">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="c88c2-137">このコードを実行すると、次の XML 出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-137">The code produces the following XML output:</span></span>  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 <span data-ttu-id="c88c2-138">詳細については、「[C# での XML ツリーの作成 (LINQ to XML)](../../../../standard/linq/create-xml-trees.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88c2-138">For more information, see [Creating XML Trees in C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="c88c2-139">ソース要素に対して操作を実行する</span><span class="sxs-lookup"><span data-stu-id="c88c2-139">Performing Operations on Source Elements</span></span>  

 <span data-ttu-id="c88c2-140">出力シーケンスには、ソース シーケンスの要素または要素のプロパティが 1 つも含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c88c2-140">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="c88c2-141">代わりに、ソース要素を入力引数として使用することで計算された値のシーケンスを出力として生成できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-141">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span>

 <span data-ttu-id="c88c2-142">次のクエリでは、円の半径を表す一連の数値を取得し、各半径での面積を計算し、計算された領域で書式設定された文字列を含む出力シーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="c88c2-142">The following query will take a sequence of numbers that represent radii of circles, calculate the area for each radius, and return an output sequence containing strings formatted with the calculated area.</span></span>

 <span data-ttu-id="c88c2-143">出力シーケンスの各文字列は、[文字列補間](../../../language-reference/tokens/interpolated.md)を使用して書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-143">Each string for the output sequence will be formatted using [string interpolation](../../../language-reference/tokens/interpolated.md).</span></span> <span data-ttu-id="c88c2-144">補間された文字列には、文字列の開始引用符の前に `$` が含まれます。操作は、補間された文字列内に配置された中かっこ内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-144">An interpolated string will have a `$` in front of the string's opening quotation mark, and operations can be performed within curly braces placed inside the interpolated string.</span></span> <span data-ttu-id="c88c2-145">これらの操作を実行すると、結果が連結されます。</span><span class="sxs-lookup"><span data-stu-id="c88c2-145">Once those operations are performed, the results will be concatenated.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c88c2-146">クエリが他のドメインに変換される場合、クエリ式でのメソッド呼び出しはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c88c2-146">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="c88c2-147">たとえば、[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] で C# の通常のメソッドを呼び出すことはできません。これは、C# のメソッドのコンテキストが SQL Server にないためです。</span><span class="sxs-lookup"><span data-stu-id="c88c2-147">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="c88c2-148">ただし、ストアド プロシージャをメソッドにマップして呼び出すことは可能です。</span><span class="sxs-lookup"><span data-stu-id="c88c2-148">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="c88c2-149">詳細については、「[ストアド プロシージャ](../../../../framework/data/adonet/sql/linq/stored-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c88c2-149">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="c88c2-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="c88c2-150">See also</span></span>

- [<span data-ttu-id="c88c2-151">統合言語クエリ (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="c88c2-151">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="c88c2-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c88c2-152">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="c88c2-153">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c88c2-153">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="c88c2-154">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="c88c2-154">LINQ to XML (C#)</span></span>](../../../../standard/linq/linq-xml-overview.md)
- [<span data-ttu-id="c88c2-155">LINQ クエリ式</span><span class="sxs-lookup"><span data-stu-id="c88c2-155">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="c88c2-156">select 句</span><span class="sxs-lookup"><span data-stu-id="c88c2-156">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
