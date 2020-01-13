---
title: 式ツリーを使用して動的クエリをビルドする方法 (C#)
ms.date: 07/20/2015
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: 6114ec13dd43a7df146b87dda00fba06d6eb870c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635900"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a><span data-ttu-id="71cbf-102">式ツリーを使用して動的クエリをビルドする方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="71cbf-102">How to use expression trees to build dynamic queries (C#)</span></span>
<span data-ttu-id="71cbf-103">LINQ では、<xref:System.Linq.IQueryable%601> を実装するデータ ソースをターゲットとする構造化されたクエリを表すために、式ツリーが使われます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="71cbf-104">たとえば、LINQ プロバイダーは、リレーショナル データ ストアのクエリを行うために、<xref:System.Linq.IQueryable%601> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="71cbf-105">C# コンパイラは、このようなデータ ソースをターゲットとするクエリをコンパイルして、実行時に式ツリーを作成するコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-105">The C# compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="71cbf-106">クエリ プロバイダーは式ツリー データ構造を走査して、データ ソースに適したクエリ言語に変換できます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="71cbf-107">LINQ では、<xref:System.Linq.Expressions.Expression%601> 型の変数に代入されるラムダ式を表すためにも、式ツリーが使われます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="71cbf-108">このトピックでは、式ツリーを使って動的な LINQ クエリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="71cbf-109">動的クエリは、コンパイル時にクエリの詳細がわからない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="71cbf-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="71cbf-110">たとえば、データをフィルター処理するための述語をエンド ユーザーが指定できるユーザー インターフェイスをアプリケーションで提供することがあります。</span><span class="sxs-lookup"><span data-stu-id="71cbf-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="71cbf-111">クエリに LINQ を使うには、このようなアプリケーションでは式ツリーを使って実行時に LINQ クエリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71cbf-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71cbf-112">例</span><span class="sxs-lookup"><span data-stu-id="71cbf-112">Example</span></span>  
 <span data-ttu-id="71cbf-113">次の例では、式ツリーを使って `IQueryable` データ ソースに対するクエリを作成して実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="71cbf-114">このコードは、次のクエリを表す式ツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-114">The code builds an expression tree to represent the following query:</span></span>  
  
 ```csharp
 companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))
          .OrderBy(company => company)
 ```
  
 <span data-ttu-id="71cbf-115">クエリ全体を構成する式を表す式ツリーの作成には、<xref:System.Linq.Expressions> 名前空間のファクトリ メソッドが使われます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="71cbf-116">標準クエリ演算子メソッドの呼び出しを表す式は、これらのメソッドの <xref:System.Linq.Queryable> の実装を参照します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="71cbf-117">最終的な式ツリーが、`IQueryable` データ ソースのプロバイダーの <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> 実装に渡されて、`IQueryable` 型の実行可能なクエリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="71cbf-118">結果は、そのクエリ変数を列挙することにより取得されます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-118">The results are obtained by enumerating that query variable.</span></span>  
  
```csharp  
// Add a using directive for System.Linq.Expressions.  
  
string[] companies = { "Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",  
                   "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",  
                   "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",  
                   "Blue Yonder Airlines", "Trey Research", "The Phone Company",  
                   "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee" };  
  
// The IQueryable data to query.  
IQueryable<String> queryableData = companies.AsQueryable<string>();  
  
// Compose the expression tree that represents the parameter to the predicate.  
ParameterExpression pe = Expression.Parameter(typeof(string), "company");  
  
// ***** Where(company => (company.ToLower() == "coho winery" || company.Length > 16)) *****  
// Create an expression tree that represents the expression 'company.ToLower() == "coho winery"'.  
Expression left = Expression.Call(pe, typeof(string).GetMethod("ToLower", System.Type.EmptyTypes));  
Expression right = Expression.Constant("coho winery");  
Expression e1 = Expression.Equal(left, right);  
  
// Create an expression tree that represents the expression 'company.Length > 16'.  
left = Expression.Property(pe, typeof(string).GetProperty("Length"));  
right = Expression.Constant(16, typeof(int));  
Expression e2 = Expression.GreaterThan(left, right);  
  
// Combine the expression trees to create an expression tree that represents the  
// expression '(company.ToLower() == "coho winery" || company.Length > 16)'.  
Expression predicateBody = Expression.OrElse(e1, e2);  
  
// Create an expression tree that represents the expression  
// 'queryableData.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))'  
MethodCallExpression whereCallExpression = Expression.Call(  
    typeof(Queryable),  
    "Where",  
    new Type[] { queryableData.ElementType },  
    queryableData.Expression,  
    Expression.Lambda<Func<string, bool>>(predicateBody, new ParameterExpression[] { pe }));  
// ***** End Where *****  
  
// ***** OrderBy(company => company) *****  
// Create an expression tree that represents the expression  
// 'whereCallExpression.OrderBy(company => company)'  
MethodCallExpression orderByCallExpression = Expression.Call(  
    typeof(Queryable),  
    "OrderBy",  
    new Type[] { queryableData.ElementType, queryableData.ElementType },  
    whereCallExpression,  
    Expression.Lambda<Func<string, string>>(pe, new ParameterExpression[] { pe }));  
// ***** End OrderBy *****  
  
// Create an executable query from the expression tree.  
IQueryable<string> results = queryableData.Provider.CreateQuery<string>(orderByCallExpression);  
  
// Enumerate the results.  
foreach (string company in results)  
    Console.WriteLine(company);  
  
/*  This code produces the following output:  
  
    Blue Yonder Airlines  
    City Power & Light  
    Coho Winery  
    Consolidated Messenger  
    Graphic Design Institute  
    Humongous Insurance  
    Lucerne Publishing  
    Northwind Traders  
    The Phone Company  
    Wide World Importers  
*/  
```  
  
 <span data-ttu-id="71cbf-119">このコードでは、`Queryable.Where` メソッドに渡される述語で固定数の式を使います。</span><span class="sxs-lookup"><span data-stu-id="71cbf-119">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="71cbf-120">ただし、ユーザー入力に依存する可変個の述語式を結合するアプリケーションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-120">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="71cbf-121">また、ユーザーからの入力に応じて、クエリで呼び出される標準クエリ演算子を変えることもできます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-121">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71cbf-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="71cbf-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="71cbf-123">System.Linq.Expressions 名前空間をインクルードします。</span><span class="sxs-lookup"><span data-stu-id="71cbf-123">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71cbf-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="71cbf-124">See also</span></span>

- [<span data-ttu-id="71cbf-125">式ツリー (C#)</span><span class="sxs-lookup"><span data-stu-id="71cbf-125">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="71cbf-126">式ツリーを実行する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="71cbf-126">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="71cbf-127">実行時における述語フィルターの動的指定</span><span class="sxs-lookup"><span data-stu-id="71cbf-127">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
